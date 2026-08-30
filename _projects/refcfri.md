---
layout: page
title: The Referendum Campaign Finance Regulation Index
description: "Paulissen, T., & Horncastle, W. (2026). Introducing the RefCFRI: A continuous indicator comparing referendum campaign finance regulation in 143 countries. Politics, 46(3), 555-569."
img: assets/img/refcfri.png
importance: 4
category: work
---
## Synthesis

The Referendum Campaign Finance Regulation Index (RefCFRI) is a continuous, empirically derived indicator that captures how intensively national referendum campaign finance is regulated across 143 countries. Building on and extending prior, largely additive or categorical measures, we assembled a global dataset of 39 legal provisions and use multiple correspondence analysis (MCA) to show that these regulations cohere along a single latent dimension interpreted as the “level of regulation.” 

The resulting index, together with the underlying qualitative dataset, provides a new tool for comparative work on direct democracy, political finance, and regulatory reform, while also being directly usable by policymakers, journalists, watchdogs, and advocacy groups.

The full paper presenting the RefCRI, written with Dr. William Horncastle, can be read at the [Politics](https://doi.org/10.1177/02633957241303708) journal. An openly available preprint can be found [here](https://www.researchgate.net/publication/387309800_Introducing_the_RefCFRI_A_continuous_indicator_comparing_referendum_campaign_finance_regulation_in_143_countries).

## RefCFRI World Map

Hover over a country to see its RefCFRI score. 

<div id="refcfri-map" style="width: 100%; height: 600px;"></div>
<div class="caption">
  Click <a href="{{ '/assets/xlm/data_refcfri.xlsx' | relative_url }}">here</a> to download the RefCFRI values in Excel format.
</div>

{% raw %}
<script src="https://cdn.plot.ly/plotly-2.27.0.min.js"></script>

<script>
document.addEventListener("DOMContentLoaded", function () {
  // Minimal test data – replace with your full RefCFRI list
  const refcfriData = [
  { iso3: "ALB", country: "Albania", value: 0.858 },
  { iso3: "DZA", country: "Algeria", value: -0.119 },
  { iso3: "AND", country: "Andorra", value: -0.043 },
  { iso3: "AGO", country: "Angola", value: -0.383 },
  { iso3: "ATG", country: "Antigua and Barbuda", value: -0.734 },
  { iso3: "ARG", country: "Argentina", value: 0.169 },
  { iso3: "ARM", country: "Armenia", value: 1.361 },
  { iso3: "AUS", country: "Australia", value: -0.015 },
  { iso3: "AUT", country: "Austria", value: -0.077 },
  { iso3: "AZE", country: "Azerbaijan", value: 0.695 },
  { iso3: "BHS", country: "Bahamas", value: 0.117 },
  { iso3: "BHR", country: "Bahrain", value: -0.734 },
  { iso3: "BLR", country: "Belarus", value: -0.439 },
  { iso3: "BLZ", country: "Belize", value: -0.734 },
  { iso3: "BEN", country: "Benin", value: -0.377 },
  { iso3: "BTN", country: "Bhutan", value: 0.806 },
  { iso3: "BOL", country: "Bolivia", value: 0.261 },
  { iso3: "BWA", country: "Botswana", value: -0.734 },
  { iso3: "BRA", country: "Brazil", value: 0.348 },
  { iso3: "BGR", country: "Bulgaria", value: -0.550 },
  { iso3: "BFA", country: "Burkina Faso", value: -0.155 },
  { iso3: "BDI", country: "Burundi", value: 0.294 },
  { iso3: "CPV", country: "Cabo Verde", value: 0.304 },
  { iso3: "CMR", country: "Cameroon", value: -0.346 },
  { iso3: "CAN", country: "Canada", value: 0.924 },
  { iso3: "CAF", country: "Central African Republic", value: -0.189 },
  { iso3: "CHL", country: "Chile", value: 0.501 },
  { iso3: "COL", country: "Colombia", value: 1.094 },
  { iso3: "COM", country: "Comoros", value: -0.487 },
  { iso3: "CRI", country: "Costa Rica", value: 0.229 },
  { iso3: "CIV", country: "Cote D'Ivoire", value: -0.295 },
  { iso3: "HRV", country: "Croatia", value: 1.023 },
  { iso3: "CUB", country: "Cuba", value: -0.676 },
  { iso3: "CZE", country: "Czechia", value: -0.117 },
  { iso3: "COD", country: "D.R. Congo", value: -0.328 },
  { iso3: "DNK", country: "Denmark", value: -0.413 },
  { iso3: "DJI", country: "Djibouti", value: -0.495 },
  { iso3: "DOM", country: "Dominican Republic", value: 0.174 },
  { iso3: "DMA", country: "Dominicana", value: -0.734 },
  { iso3: "TLS", country: "East Timor", value: -0.008 },
  { iso3: "ECU", country: "Ecuador", value: 1.180 },
  { iso3: "SLV", country: "El Salvador", value: -0.461 },
  { iso3: "EST", country: "Estonia", value: 0.038 },
  { iso3: "SWZ", country: "Eswatini", value: -0.734 },
  { iso3: "ETH", country: "Ethiopia", value: -0.160 },
  { iso3: "FSM", country: "Federated States of Micronesia", value: -0.734 },
  { iso3: "FJI", country: "Fiji", value: -0.086 },
  { iso3: "FIN", country: "Finland", value: -0.117 },
  { iso3: "FRA", country: "France", value: 0.963 },
  { iso3: "GMB", country: "Gambia", value: -0.413 },
  { iso3: "GEO", country: "Georgia", value: 0.451 },
  { iso3: "GHA", country: "Ghana", value: -0.197 },
  { iso3: "GRC", country: "Greece", value: 1.207 },
  { iso3: "GRD", country: "Grenada", value: -0.734 },
  { iso3: "GTM", country: "Guatemala", value: 0.632 },
  { iso3: "HUN", country: "Hungary", value: 0.009 },
  { iso3: "ISL", country: "Iceland", value: -0.058 },
  { iso3: "IRN", country: "Iran", value: -0.188 },
  { iso3: "IRQ", country: "Iraq", value: -0.166 },
  { iso3: "IRL", country: "Ireland", value: -0.025 },
  { iso3: "ITA", country: "Italy", value: 0.092 },
  { iso3: "JAM", country: "Jamaica", value: -0.168 },
  { iso3: "JPN", country: "Japan", value: -0.147 },
  { iso3: "KAZ", country: "Kazakhstan", value: -0.279 },
  { iso3: "KEN", country: "Kenya", value: 1.007 },
  { iso3: "KIR", country: "Kiribati", value: -0.734 },
  { iso3: "KGZ", country: "Kyrgyzstan", value: 0.295 },
  { iso3: "LVA", country: "Latvia", value: 0.691 },
  { iso3: "LSO", country: "Lesotho", value: -0.734 },
  { iso3: "LBR", country: "Liberia", value: 1.272 },
  { iso3: "LIE", country: "Liechtenstein", value: -0.443 },
  { iso3: "LTU", country: "Lithuania", value: 1.105 },
  { iso3: "LUX", country: "Luxembourg", value: -0.164 },
  { iso3: "MDG", country: "Madagascar", value: 0.354 },
  { iso3: "MWI", country: "Malawi", value: -0.244 },
  { iso3: "MDV", country: "Maldives", value: -0.519 },
  { iso3: "MLI", country: "Mali", value: -0.337 },
  { iso3: "MLT", country: "Malta", value: -0.093 },
  { iso3: "MHL", country: "Marshall Islands", value: -0.518 },
  { iso3: "MRT", country: "Mauritania", value: -0.447 },
  { iso3: "MUS", country: "Mauritius", value: -0.734 },
  { iso3: "MEX", country: "Mexico", value: 0.423 },
  { iso3: "MDA", country: "Moldova", value: 1.113 },
  { iso3: "MNG", country: "Mongolia", value: 0.080 },
  { iso3: "MNE", country: "Montenegro", value: 1.044 },
  { iso3: "MAR", country: "Morocco", value: -0.028 },
  { iso3: "MOZ", country: "Mozambique", value: -0.372 },
  { iso3: "MMR", country: "Myanmar", value: -0.648 },
  { iso3: "NAM", country: "Namibia", value: -0.334 },
  { iso3: "NRU", country: "Nauru", value: -0.734 },
  { iso3: "NPL", country: "Nepal", value: -0.218 },
  { iso3: "NZL", country: "New Zealand", value: 0.171 },
  { iso3: "NER", country: "Niger", value: -0.333 },
  { iso3: "NGA", country: "Nigeria", value: 0.273 },
  { iso3: "NOR", country: "Norway", value: -0.089 },
  { iso3: "PAK", country: "Pakistan", value: -0.298 },
  { iso3: "PLW", country: "Palau", value: -0.734 },
  { iso3: "PAN", country: "Panama", value: 0.210 },
  { iso3: "PRY", country: "Paraguay", value: 0.298 },
  { iso3: "PER", country: "Peru", value: 0.262 },
  { iso3: "PHL", country: "Philippines", value: -0.507 },
  { iso3: "POL", country: "Poland", value: 0.214 },
  { iso3: "PRT", country: "Portugal", value: 0.677 },
  { iso3: "COG", country: "Republic of Congo", value: -0.211 },
  { iso3: "ROK", country: "Republic of Korea", value: 0.173 },
  { iso3: "ROU", country: "Romania", value: 1.265 },
  { iso3: "RUS", country: "Russia", value: 1.139 },
  { iso3: "RWA", country: "Rwanda", value: -0.474 },
  { iso3: "VCT", country: "Saint Vincent and the Grenadines", value: -0.734 },
  { iso3: "WSM", country: "Samoa", value: -0.734 },
  { iso3: "STP", country: "São Tomé and Príncipe", value: -0.220 },
  { iso3: "SEN", country: "Senegal", value: 0.003 },
  { iso3: "SRB", country: "Serbia", value: 0.798 },
  { iso3: "SYC", country: "Seychelles", value: -0.167 },
  { iso3: "SLE", country: "Sierra Leone", value: -0.138 },
  { iso3: "SGP", country: "Singapore", value: -0.340 },
  { iso3: "SVK", country: "Slovakia", value: -0.023 },
  { iso3: "SVN", country: "Slovenia", value: 1.122 },
  { iso3: "ZAF", country: "South Africa", value: -0.077 },
  { iso3: "SSD", country: "South Sudan", value: -0.141 },
  { iso3: "ESP", country: "Spain", value: 0.308 },
  { iso3: "LKA", country: "Sri Lanka", value: -0.734 },
  { iso3: "SWE", country: "Sweden", value: -0.413 },
  { iso3: "CHE", country: "Switzerland", value: -0.142 },
  { iso3: "SYR", country: "Syria", value: -0.088 },
  { iso3: "TJK", country: "Tajikistan", value: -0.301 },
  { iso3: "TZA", country: "Tanzania", value: -0.110 },
  { iso3: "THA", country: "Thailand", value: -0.008 },
  { iso3: "TGO", country: "Togo", value: 0.069 },
  { iso3: "TUN", country: "Tunisia", value: 0.542 },
  { iso3: "TUR", country: "Türkiye", value: 0.018 },
  { iso3: "TKM", country: "Turkmenistan", value: -0.328 },
  { iso3: "TUV", country: "Tuvalu", value: -0.734 },
  { iso3: "UGA", country: "Uganda", value: 0.202 },
  { iso3: "UKR", country: "Ukraine", value: 1.110 },
  { iso3: "GBR", country: "United Kingdom", value: 0.919 },
  { iso3: "URY", country: "Uruguay", value: 0.002 },
  { iso3: "UZB", country: "Uzbekistan", value: -0.047 },
  { iso3: "VUT", country: "Vanuatu", value: -0.734 },
  { iso3: "VEN", country: "Venezuela", value: 0.600 },
  { iso3: "YEM", country: "Yemen", value: -0.207 },
  { iso3: "RNR", country: "Zambia", value: -0.734 },
  { iso3: "ZWE", country: "Zimbabwe", value: -0.546 }
];

  const data = [{
    type: "choropleth",
    locations: refcfriData.map(d => d.iso3),
    locationmode: "ISO-3",
    z: refcfriData.map(d => d.value),
    text: refcfriData.map(d => `${d.country}: ${d.value.toFixed(3)}`),
    // Dark-friendly colorscale
    colorscale: [
      [0.0, "#0d47a1"],  // deep blue
      [0.5, "#ab47bc"],  // purple
      [1.0, "#ffca28"]   // amber
    ],
    colorbar: {
      title: "RefCFRI",
      tickfont: { color: "#e0e0e0" },
      titlefont: { color: "#e0e0e0" },
      outlinewidth: 0
    },
    hovertemplate: "%{text}<extra></extra>"
  }];

  const layout = {
    template: "plotly_dark",  // base dark theme
    margin: { t: 10, r: 10, b: 10, l: 10 },
    paper_bgcolor: "rgba(0,0,0,0)",   // transparent to match site background
    plot_bgcolor: "rgba(0,0,0,0)",
    font: {
      family: "system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
      color: "#e0e0e0"
    },
    geo: {
      projection: { type: "natural earth" },
      showframe: false,
      showcoastlines: true,
      coastlinecolor: "#555555",
      coastlinewidth: 0.5,
      showcountries: true,
      countrycolor: "#444444",
      countrywidth: 0.5,
      showland: true,
      landcolor: "#111111",
      showocean: true,
      oceancolor: "#050505",
      bgcolor: "rgba(0,0,0,0)"
    }
  };

  Plotly.newPlot("refcfri-map", data, layout, { responsive: true });
});
</script>
{% endraw %}

Our case selection consist of UN-members where: (a) the legislative framework (constitution or other piece of legislation) allows for the organisation of national referendums, or (b) that have organised an ad hoc referendum over the last 50 years. 

Some cases had to be omitted due to ongoing civil conflict (Somalia) and sovereignty disputes (Cyprus). Afghanistan was also left out, following the transition to Taliban leadership, while we excluded North Macedonia due to uncertainty on which regulations apply. 

Finally, we omitted those cases which, despite showing evidence of financing regulations, did not have original legislative sources available. This was the case for Chad, Egypt, Equatorial Guinea, Gabon, Guinea, Honduras and Qatar. Our final sample covers 143 countries: 44 from Africa, 27 from Asia, 36 from Europe, 15 from North America, 11 from Oceania and 10 from South America.


## The Underlying Data on Referendum Campaign Finance Regimes

To construct the RefCFRI, the following questionaire below was developed. Click [here](/assets/xlm/data_global.csv) to download a CSV file that shows how each country was coded for each category.  

<div class="table-responsive mt-4 mb-4">
  <table class="table table-sm table-striped">
    <thead class="thead-light">
      <tr>
        <th scope="col">Code</th>
        <th scope="col">Question</th>
      </tr>
    </thead>
    <tbody>
      <!-- Spending Limits -->
      <tr class="table-secondary">
        <td colspan="2"><strong>Spending Limits</strong></td>
      </tr>
      <tr>
        <td>LIMSPENDTYPE</td>
        <td>Limits on what actors can spend money on?</td>
      </tr>
      <tr>
        <td>LIMSPENDPARTY</td>
        <td>Limits on spending political parties?</td>
      </tr>
      <tr>
        <td>LIMSPENDOTHER</td>
        <td>Limits on spending other actors?</td>
      </tr>
      <tr>
        <td>LIMSPENDMEDIA</td>
        <td>Limits on media advertising spending?</td>
      </tr>
      <tr>
        <td>LIMSPENDONLINE</td>
        <td>Limits on online media advertising spending?</td>
      </tr>
      <tr>
        <td>RESTRONLINE</td>
        <td>Other restrictions concerning online media advertising?</td>
      </tr>

      <!-- Public Funding -->
      <tr class="table-secondary">
        <td colspan="2"><strong>Public Funding</strong></td>
      </tr>
      <tr>
        <td>PUBFUNDPARTY</td>
        <td>Direct public funding to parties?</td>
      </tr>
      <tr>
        <td>PUBFUNDOTHER</td>
        <td>Direct public funding to other actors?</td>
      </tr>
      <tr>
        <td>FREEMEDIAPARTY</td>
        <td>Free or subsidised access to media for parties?</td>
      </tr>
      <tr>
        <td>FREEMEDIAOTHER</td>
        <td>Free or subsidised access to media for other actors?</td>
      </tr>
      <tr>
        <td>INDIRPUBFUND</td>
        <td>Any other form of indirect public funding?</td>
      </tr>

      <!-- Transparency -->
      <tr class="table-secondary">
        <td colspan="2"><strong>Transparency</strong></td>
      </tr>
      <tr>
        <td>FINREPPARTY</td>
        <td>Parties have to report on their referendum campaign finances?</td>
      </tr>
      <tr>
        <td>FINREPOTHER</td>
        <td>Other actors have to report on their referendum campaign finances?</td>
      </tr>
      <tr>
        <td>FINREPPUBLIC</td>
        <td>Information made public?</td>
      </tr>
      <tr>
        <td>FINREPDONOR</td>
        <td>Actors have to reveal identity of donors?</td>
      </tr>
      <tr>
        <td>FINREPINCOME</td>
        <td>Reports have to include info on itemised income?</td>
      </tr>
      <tr>
        <td>FINREPSPEND</td>
        <td>Reports have to include info on itemised spending?</td>
      </tr>
      <tr>
        <td>TRANSPONLINE</td>
        <td>Additional provisions regarding online campaigning?</td>
      </tr>
      <tr>
        <td>SANCTIONS</td>
        <td>Sanctions provided for infractions?</td>
      </tr>
      <tr>
        <td>MONITORBODY</td>
        <td>Dedicated body that monitors whether regulations are followed?</td>
      </tr>
      <tr>
        <td>REGPARTY</td>
        <td>Parties need to register with a monitoring body before campaigning?</td>
      </tr>
      <tr>
        <td>REGREQPARTY</td>
        <td>If yes: parties need to fulfil specific requirements to be eligible?</td>
      </tr>
      <tr>
        <td>REGOTHER</td>
        <td>Other actors need to register with a monitoring body before campaigning?</td>
      </tr>
      <tr>
        <td>REGREQOTHER</td>
        <td>If yes: other actors need to fulfil specific requirements to be eligible?</td>
      </tr>

      <!-- Private Income -->
      <tr class="table-secondary">
        <td colspan="2"><strong>Private Income</strong></td>
      </tr>
      <tr>
        <td>DONFORPARTY</td>
        <td>Ban on donations from foreign interests to political parties?</td>
      </tr>
      <tr>
        <td>DONFOROTHER</td>
        <td>Ban on donations from foreign interests to other actors?</td>
      </tr>
      <tr>
        <td>DONCORPPARTY</td>
        <td>Ban on corporate donations to political parties?</td>
      </tr>
      <tr>
        <td>DONCORPOTHER</td>
        <td>Ban on corporate donations to other actors?</td>
      </tr>
      <tr>
        <td>DONTUPARTY</td>
        <td>Ban on donations from trade unions to political parties?</td>
      </tr>
      <tr>
        <td>DONTUOTHER</td>
        <td>Ban on donations from trade unions to other actors?</td>
      </tr>
      <tr>
        <td>DONGOVCONPARTY</td>
        <td>Ban on donations from corporations with government contracts to political parties?</td>
      </tr>
      <tr>
        <td>DONGOVCONOTHER</td>
        <td>Ban on donations from corporations with government contracts to other actors?</td>
      </tr>
      <tr>
        <td>DONGOVCORPPARTY</td>
        <td>Ban on donations from corporations with partial government ownership to parties?</td>
      </tr>
      <tr>
        <td>DONGOVCORPOTHER</td>
        <td>Ban on donations from corporations with partial government ownership to other actors?</td>
      </tr>
      <tr>
        <td>DONLIMPARTY</td>
        <td>Limit on the amount a donor can contribute to a political party?</td>
      </tr>
      <tr>
        <td>DONLIMOTHER</td>
        <td>Limit on the amount a donor can contribute to other actors?</td>
      </tr>
      <tr>
        <td>DONIKLIMPARTY</td>
        <td>Limit on in-kind donations to political parties?</td>
      </tr>
      <tr>
        <td>DONIKLIMOTHER</td>
        <td>Limit on in-kind donations to other actors?</td>
      </tr>
      <tr>
        <td>DONBANK</td>
        <td>Donations go through the banking system?</td>
      </tr>
    </tbody>
  </table>
</div>

<p class="caption text-muted">
  Questionnaire for data collection on referendum political finance regimes.
</p>
