### Phase 1: Discovery & Requirements (The "Why")

- **Stakeholder Alignment:** Identifying who this is for (Veterans, families, historians).
- **Functional Requirements:** "Users must be able to filter by unit."
- **Non-Functional Requirements (NFRs):** "The map must load in under 2 seconds" or "The site must be accessible (WCAG 2.1 compliance) for users with visual impairments."

### Phase 2: System Design & Architecture (The "How")

- **Tech Stack Selection:** Deciding on React, D3.js, and a backend
- **Data Modeling:** Designing the schema for the KIA records to ensure "10th Mountain" and "1-5 Infantry" are queryable.
- **The Design Doc:** A technical blueprint shared with peers to catch logic flaws before a single line of code is written.

### Phase 3: UI/UX Design (The "Stitch" Phase)

- **High-Fidelity Wireframes:** Using tools like Stitch or Figma to finalize the "Field of Light" aesthetic.
- **Prototyping:** Testing the "Zoom-to-Province" flow to ensure it doesn't feel disorienting.

### Phase 4: Implementation (The "Sprint")

- **Frontend Development:** Building the D3.js map and the responsive layout.
- **Backend Development:** Setting up the API and the data ingestion scripts to clean the datasets.
- **CI/CD Pipeline:** Setting up automated workflows (GitHub Actions) so every time you "push" code, it is checked for errors.

### Phase 5: Testing & Quality Assurance (The "Shield")

- **Unit Testing:** Testing individual functions (e.g., "Does the date filter correctly handle leap years?").
- **Integration Testing:** Ensuring the frontend talks to the database correctly.
- **User Acceptance Testing (UAT):** Having actual veterans or family members use the beta to see if the interface feels respectful and intuitive.
- **Performance Testing:** Simulating 1,000 users hitting the map at once.

### Phase 6: Security & Compliance (The "Lock")

- **Data Privacy:** Ensuring no sensitive, non-public data was accidentally scraped.
- **Dependency Scanning:** Checking your NPM packages for vulnerabilities.

### Phase 7: Deployment & Release (The "Launch")

- **Staging Environment:** Deploying to a private URL that looks exactly like the real site for final checks.
- **Production Deployment:** Moving the site to the public URL.
- **Blue/Green or Canary Release:** Releasing the site to only 10% of users first to ensure nothing breaks in the "wild."

### Phase 8: Maintenance & Monitoring (The "Life")

- **Error Tracking:** Using tools like Sentry to see if the map crashes on someone’s specific browser (like an old version of Safari).
- **Analytics:** Seeing which provinces people visit most to improve the UI.

---

### Roadmap

| Checkpoint               | Action Item                                                                                                                          |
| :----------------------- | :----------------------------------------------------------------------------------------------------------------------------------- |
| **The Data Audit**       | Before you release, manually verify a handful of records against the "Honor the Fallen" database. Accuracy is the primary "feature." |
| **Cross-Browser Test**   | D3.js can behave differently on a mobile Chrome browser vs. a Desktop Edge browser. Test both.                                       |
| **The "Respect" Review** | Once the site is on a staging link, send it to veterans for a "gut check" on the UX.                                                 |
