# Power-Audit
Interactive power quality & energy monitoring dashboard — real-time phasor diagrams, harmonic spectrum analysis, PF correction calculator, and IEEE 519 compliance reporting. Built with vanilla JS + Chart.js.
# PowerAudit: Power Quality & Energy Monitoring Dashboard

PowerAudit is a production-quality static web dashboard for an electrical engineering portfolio. It simulates a real-time industrial power-quality audit tool with live KPI cards, phasor visualization, waveform analysis, harmonic spectrum checks, power-factor correction sizing, and an exportable energy audit report.

The project is designed for GitHub Pages deployment: it is a single HTML file with inline CSS and JavaScript, with no build tools, frameworks, or persistent browser storage.

## Tech Stack

- HTML5
- CSS3 with custom properties for theming
- Vanilla JavaScript ES6+
- Chart.js v4 via CDN
- Lucide Icons via CDN
- Google Fonts: Inter and DM Mono
- Static deployment target: GitHub Pages

## Features

- Dark mode by default with light-mode toggle
- Responsive fixed-sidebar dashboard layout with mobile top navigation
- Live KPI cards for P, Q, S, PF, THD_V, and THD_I
- Canvas-based phasor diagram with voltage/current magnitude scaling and phase-angle interaction
- Chart.js power triangle and before/after correction triangle
- Waveform analysis using 256 sample points per cycle
- Harmonic spectrum charts with IEEE 519 5% limit indicators
- Power factor correction calculator for capacitor bank sizing
- Printable energy audit report with CSV export

## Formulas Used

```text
V_peak = V_rms * sqrt(2)
I_peak = I_rms * sqrt(2)
omega = 2 * pi * f

P = V_rms * I_rms * cos(phi)
Q = V_rms * I_rms * sin(phi)
S = V_rms * I_rms
PF = cos(phi) = P / S

THD_V = sqrt(h3_v^2 + h5_v^2 + h7_v^2) / 1.0 * 100
THD_I = sqrt(h3_i^2 + h5_i^2 + h7_i^2) / 1.0 * 100

Q_c = P_kW * 1000 * (tan(phi_1) - tan(phi_2))
C_uF = Q_c / (omega * V_rms^2) * 1e6

Monthly energy savings estimate = (S_old - S_new) * PF_old * 720
Monthly cost savings = monthly energy savings estimate * 0.12
```

## Running Locally

Open `power-dashboard.html` directly in a browser:

```text
power-dashboard.html
```

Internet access is only required for CDN-loaded fonts, Chart.js, and Lucide Icons.

## Deployment

1. Commit `power-dashboard.html` and `README.md` to a GitHub repository.
2. In GitHub, open **Settings > Pages**.
3. Select the branch and root folder.
4. Visit the generated GitHub Pages URL.

If GitHub Pages needs an `index.html`, either rename `power-dashboard.html` to `index.html` or add a simple redirect page.
