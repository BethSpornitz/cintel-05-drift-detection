# Continuous Intelligence

This site provides documentation for this project.
Use the navigation to explore module-specific materials.

## How-To Guide

Many instructions are common to all our projects.

See
[⭐ **Workflow: Apply Example**](https://denisecase.github.io/pro-analytics-02/workflow-b-apply-example-project/)
to get these projects running on your machine.

## Project Documentation Pages (docs/)

- **Home** - this documentation landing page
- **Project Instructions** - instructions specific to this module
- **Your Files** - how to copy the example and create your version
- **Glossary** - project terms and concepts

## Custom Project

### Dataset
This project used two copied system metrics datasets: `reference_metrics_bethspornitz.csv` and `current_metrics_bethspornitz.csv`. The reference dataset represents earlier expected system behavior, and the current dataset represents more recent system behavior. Each dataset contains observations of system performance including requests, errors, and total latency.

### Signals
The project compared average requests, average errors, and average latency between the reference and current periods. It calculated the difference between these values and used drift flags to determine when the change exceeded a threshold. Additional signals were created to classify drift severity and provide an overall system status.

### Experiments
I modified the original drift detection pipeline by creating a new file named `drift_detector_bethspornitz.py`. I updated the dataset paths, lowered the drift thresholds to make the detector more sensitive, and added new logic to classify drift severity as no_drift, moderate_drift, or high_drift. I also added an overall drift status field and exported the results to both CSV and Excel formats for improved readability.

### Results
After running the modified pipeline, all three metrics (requests, errors, and latency) were flagged as drifting. Each metric was classified as high_drift, and the overall system status was labeled as attention_needed. The results showed that the differences between the current and reference periods exceeded the defined thresholds.

### Interpretation
The system is experiencing increased load along with degraded performance. Requests, errors, and latency all increased significantly compared to the reference period. This suggests that the system may be under strain or encountering issues that require investigation. The addition of severity levels and an overall status helps prioritize response and provides clearer insight into system health.

## Additional Resources

- [Suggested Datasets](https://denisecase.github.io/pro-analytics-02/reference/datasets/cintel/)
