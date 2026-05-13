# Inquiry → Submit Bell Curve Dashboard

A lightweight, executive-friendly Shiny dashboard for analyzing the time between inquiry and application submission across academic programs.

Built for enrollment and admissions teams, this app visualizes funnel velocity using density distributions (“bell curves”), helping identify patterns in student conversion timelines across programs and terms.

---

## Features

- 📈 Interactive density (“bell curve”) visualization
- 🎯 Filter by individual academic program
- 📅 Optional term filtering
- 📊 Median and interquartile range (IQR) reference overlays
- 🧮 Automated summary statistics table
- 🎨 Clean publication-style design using `theme_tufte()`
- 💾 Export charts as high-resolution PNGs
- 🧹 Robust date parsing across inconsistent CRM exports

---

## Preview

The dashboard allows users to:

- Compare overall inquiry-to-submit timing
- Identify programs with faster or slower applicant conversion cycles
- Explore spread and variance in applicant behavior
- Quickly export visualizations for reporting or presentations

---

## Tech Stack

- R
- Shiny
- tidyverse
- ggplot2
- gt
- lubridate
- janitor
- ggthemes

---

## Expected Data Structure

The application expects a CSV export containing the following columns:

| Column Name | Description |
|---|---|
| `date_of_inquiry` | Initial inquiry date |
| `application_submit_date` | Application submission date |
| `active_major_calculated` | Program / major name |
| `active_term_calculated` | Entry term |

The app automatically:

- Cleans column names
- Parses multiple date formats
- Removes invalid or negative timelines
- Filters extreme outliers (>500 days)

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/inquiry-submit-density-dashboard.git
cd inquiry-submit-density-dashboard
```

Install required packages:

```r
install.packages(c(
  "shiny",
  "tidyverse",
  "lubridate",
  "janitor",
  "ggthemes",
  "gt"
))
```

---

## Configuration

Update the data source path inside `app.R`:

```r
DATA_PATH <- "C:/Users/Todd/Dropbox/Daily Export/totalfunnelexport.csv"
```

---

## Run the App

```r
shiny::runApp()
```

Or open `app.R` in RStudio and click:

> Run App

---

## Example Use Cases

### Enrollment Analytics
Monitor inquiry-to-application behavior across graduate programs.

### Funnel Optimization
Identify programs with long conversion windows that may need revised outreach strategies.

### Leadership Reporting
Generate clean exportable visuals for cabinet presentations or enrollment reviews.

### Market Insights
Compare applicant responsiveness across terms or academic offerings.

---

## Future Enhancements

Potential roadmap ideas:

- Historical trend comparison
- Yield-stage analytics
- Deposit conversion overlays
- Predictive funnel modeling
- Interactive percentile tooltips
- Automated report exports
- Deployment via Posit Connect or ShinyApps.io

---

## Design Philosophy

This project emphasizes:

- Minimalist analytical design
- High signal-to-noise visualizations
- Fast exploratory filtering
- Accessible admissions intelligence tooling

Inspired by publication-style statistical graphics and operational dashboard workflows.

---

## Author

Todd — Enrollment analytics and admissions strategy professional focused on modern higher education data storytelling.

---

## License

MIT License

Feel free to adapt, extend, and reuse for institutional analytics projects.
