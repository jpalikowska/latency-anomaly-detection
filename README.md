# Latency Anomaly Detection

Anomaly detection methods for synthetic p99 latency data in distributed systems —
short-term regressions and long-term degradation trends, evaluated against
injected ground-truth anomalies.

## Contents
- `report.pdf` — full report (methods, results, discussion)
- `anomaly_detection.ipynb` — data generation + all experiments

## Summary
Anomaly detection difficulty depends strongly on both anomaly type and environment stability. For short-term anomalies, CUSUM gives the best point-level performance for sustained multi-day regressions, but event-level evaluation favors simpler threshold methods (Kalman, rolling z-score, EWMA, Shewhart). For long-term anomalies, results are weaker overall and linear slope performs best.

## Methods evaluated
Short-term: rolling z-score, robust z-score, IQR, CUSUM, Kalman residual, Shewhart, EWMA
Long-term: linear slope, Mann-Kendall, rolling slope (+ long-window CUSUM/EWMA/IQR)
