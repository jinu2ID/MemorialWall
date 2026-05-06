## 1. Stakeholder Alignment

| Stakeholder Group            | Primary Interest                                        | Role in Your Project                                                          |
| :--------------------------- | :------------------------------------------------------ | :---------------------------------------------------------------------------- |
| **Gold Star Families**       | Dignity, accuracy, and ease of finding their loved one. | **The North Star:** UX must be simple and respectful.                         |
| **Veterans / Unit Orgs**     | Unit pride, historical context of deployment.           | **The Subject Matter Experts:** Data must accurately reflect unit structures. |
| **Researchers / Historians** | Data integrity, filtering capabilities, and sources.    | **The Fact Checkers:** Need "Methodology" and "Source" links.                 |
| **General Public**           | Education and understanding of the scale of the war.    | **The Audience:** Need an intuitive, low-barrier interface.                   |

---

## 2. Functional Requirements

- **FR1. Interactive GIS Map:** Users shall be able to view a map of Afghanistan with 34 selectable province boundaries.
- **FR2. Temporal Filtering:** Users shall be able to filter KIA records by year (2001–2021) using a timeline slider.
- **FR3. Unit/Branch Filtering:** Users shall be able to filter names by Service Branch (Army, Marines, etc.) and Unit.
- **FR3.1 Unit Hierarchy:** The system SHALL support hierarchical unit filtering, allowing users to filter by broad categories (e.g., "1st Infantry Division") and then drill down to specific sub-units (e.g., "2nd Brigade Combat Team").
- **FR3.2. Unit Level Filtering:** The system SHALL support unit filtering down to the Battalion level or the Airforce/Navy equivalent.
- **FR4. Zoom-to-Region:** Clicking a province shall trigger a D3.js transition that zooms the camera and reveals granular "Field of Light" pins.
- **FR5. The "Memorial Wall":** A searchable list of names must be present, updating in real-time based on map filters.
- **FR6. Individual Tributes:** Clicking a name/pin shall open a modal/view with the soldier’s rank, unit, and date of casualty.
- **FR7. Unique Resource Identifiers (Permalinks)**: The system SHALL generate and support unique, persistent URLs for specific filtered states (e.g., specific province, year range, or unit) and for individual personnel records to enable direct sharing and deep-linking.
- **FR8. User-Initiated Data Correction Workflow:** The system SHALL provide a dedicated interface for users to submit factual corrections or report data discrepancies. Submissions MUST be routed to a moderation queue or an administrative logging system. This could be a simple form that sends an email or logs a GitHub issue.
- **FR8.1. Data Provenance and Source Attribution:** Each KIA record displayed on the map or in the memorial wall MUST include a link to its source(s) (e.g., DoD DCAS, iCasualties). This ensures transparency and allows users to verify the information independently.
- **FR8.2. User Feedback Loop for Data Corrections:** The system SHALL implement a feedback mechanism to inform users about the status of their submitted corrections (e.g., "Received," "Under Review," "Approved," "Rejected"). This could be achieved through email notifications or a user dashboard that tracks submission statuses.
- **FR8.3. Data Verification.** The system SHALL implement a verification process for submitted corrections, which may include cross-referencing with existing data, consulting additional sources, and manual review by administrators. This process is crucial to maintain the integrity and accuracy of the dataset.
- **FR9. Global Full-Text Search:** The system SHALL implement a global search interface allowing users to locate individual records by name. Successful search results MUST allow the user to navigate directly to the specific geographic pin and biographical card.
- **FR10. Biographical Media Presentation:** The system SHALL provide a modal or "lightbox" interface to display soldier photographs and extended biographical data. This interface MUST NOT require a full page reload, maintaining the user’s current map zoom and filter state.

---

## 3. Non-Functional Requirements

These define the quality attributes of the system. In a professional project, these are often more important than the features.

- **NFR1: Performance.** The map must maintain **60 FPS** during zooms. Total page load should be under **2.5 seconds** (achieved via CDN and JSON compression).
- **NFR2: Accuracy.** Data must be cross-referenced with at least two primary sources (DoD DCAS and iCasualties). There must be a "Report Error" feature.
- **NFR3: Accessibility (WCAG 2.2).** The site must be navigable via keyboard and compatible with screen readers. Colors (like the gold/charcoal) must meet contrast ratios for the visually impaired.
- **NFR4: Ethical UI (The "Solemnity" Rule).** No bright "danger" colors (reds/hotspots). UI must remain muted and respectful. No commercial ads or intrusive trackers.
- **NFR5: Responsiveness.** The UI must adapt to mobile devices (portrait mode) by stacking the map above the list, though the "full experience" is optimized for Desktop.
- **NFR6: Data Privacy.** The system must not collect personally identifiable information (PII) from users. Any user-submitted corrections should be anonymized and stored securely, with clear communication about how the data will be used.
- **NFR7: Search Engine Indexability (SEO).** The system SHALL ensure that individual memorial records are crawlable by search engine bots. This SHALL be achieved through server-side rendering (SSR) or pre-rendering of individual record paths.
- **NFR8: Long-term Operational Sustainability.** The system architecture SHALL prioritize low-cost maintenance. The application MUST be deployable as a static site (via Static Site Generation) to minimize server overhead and ensure 99.9% availability on standard object storage.
- **NFR9: Elastic Traffic Scalability.** The system SHALL be capable of handling a 100x surge in concurrent users (e.g., during national holidays or news events) without manual intervention or service interruption. This SHALL be achieved through the use of a distributed Content Delivery Network (CDN).

---

### Phase 1: Success Criteria (Definition of Done)

To move to **Phase 2 (System Design)**, answer "Yes" to the following:

1.  Do I have a cleaned dataset (even a small sample) that fits my schema?
2.  Does my Stitch design account for all the Functional Requirements above?
3.  Have I identified a source for the Afghanistan TopoJSON file?
