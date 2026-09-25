---
layout: post
title: Cell Division Exercises
date: 2026-09-20
description: Practice visualizing the number of chromosomes and chromatids through stages of cell division.
tags: scicomm
categories: bio202
related_posts: false
pretty_table: true
---

It can be confusing to keep track of the genetic materials through different stages of cell divisions, since they are packed into slightly different units. I think working through the numbers of chromosomes and chromatids through mitotic and meiotic phases can be a good exercise to understand the distinctions between different levels of building blocks of DNA. 

Fill in the table, and the chart below should update and visualize in real-time! 

<div class="cc-wrapper">
  <style>
    .cc-wrapper {
      font-family: inherit;
      color: inherit;
      margin: 2rem 0;
      width: 100%;
    }
    .cc-wrapper table {
      width: 100% !important;
      border-collapse: collapse !important;
      margin-bottom: 1.5rem !important;
      font-size: 0.9rem;
    }
    .cc-wrapper th, .cc-wrapper td {
      padding: 8px 10px !important;
      text-align: center;
      border-bottom: 1px solid var(--global-divider-color);
    }
    .cc-wrapper th{
      color: var(--global-2nd-color);
    }
    .cc-wrapper th:first-child, .cc-wrapper td:first-child {
      text-align: left !important;
    }
    .cc-wrapper .cc-group-row td {
      font-weight: bold;
      background-color: var(--global-bg-color-2, rgba(0,0,0,0.03));
      text-align: left !important;
    }
    .cc-wrapper input[type="number"] {
      width: 65px !important;
      max-width: 100% !important;
      padding: 4px 6px !important;
      text-align: center;
      border: 1px solid var(--global-divider-color);
      border-radius: 4px;
      background: var(--global-bg-color);
      color: var(--global-text-color);
      box-sizing: border-box;
    }
    .cc-chart-container {
      position: relative;
      width: 100%;
      height: 320px;
      max-height: 400px;
      margin-top: 1rem;
    }
  </style>
    <h1>Mitosis</h1>
    <div class="cc-btn-group">
        <button type="button" id="cc-btn-preset" class="cc-btn">Load Human Somatic (2n = 46)</button>
        <button type="button" id="cc-btn-clear" class="cc-btn">Clear Table</button>
        <button type="button" id="cc-btn-save" class="cc-btn">📥 Save Chart Image</button>
    </div>

  <div style="overflow-x: auto;">
    <table id="cc-table">
      <thead>
        <tr>
          <th style="text-align:left;">Stage</th>
          <th># Chromosomes</th>
          <th># Chromatids</th>
          <th># Centromeres</th>
          <th># DNA Molecules</th>
        </tr>
      </thead>
      <tbody>
        <tr class="cc-group-row">
            <td colspan="5" style="color: var(--global-3rd-color)">Interphase</td>
        </tr>
        <tr>
          <td class="cc-stage">G1</td>
          <td><input type="number" min="0" data-row="G1" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="G1" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="G1" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="G1" data-field="dna"></td>
        </tr>
        <tr>
          <td class="cc-stage">G2</td>
          <td><input type="number" min="0" data-row="G2" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="G2" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="G2" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="G2" data-field="dna"></td>
        </tr>
        <tr class="cc-group-row">
            <td colspan="5" style="color: var(--global-3rd-color)">Mitosis</td>
        </tr>
        <tr>
          <td class="cc-stage">Prophase</td>
          <td><input type="number" min="0" data-row="pro" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="pro" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="pro" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="pro" data-field="dna"></td>
        </tr>
        <tr>
          <td class="cc-stage">Metaphase</td>
          <td><input type="number" min="0" data-row="meta" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meta" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meta" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meta" data-field="dna"></td>
        </tr>
        <tr>
          <td class="cc-stage">Anaphase</td>
          <td><input type="number" min="0" data-row="ana" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="ana" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="ana" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="ana" data-field="dna"></td>
        </tr>
        <tr>
          <td class="cc-stage">Telophase</td>
          <td><input type="number" min="0" data-row="telo" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="telo" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="telo" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="telo" data-field="dna"></td>
        </tr>
        <tr class="cc-group-row">
            <td colspan="5" style="color: var(--global-3rd-color)">Post-Cytokinesis</td>
        </tr>
        <tr>
          <td class="cc-stage">Daughter Cell</td>
          <td><input type="number" min="0" data-row="mit-inter" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="mit-inter" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="mit-inter" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="mit-inter" data-field="dna"></td>
        </tr>
      </tbody>
    </table>
  </div>
<caption><h4 style="text-align: center">Genetic materials overtime in mitosis</h4></caption>
<div class="cc-chart-container">
    <canvas id="ccLineChart"></canvas>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-annotation@3.0.1/dist/chartjs-plugin-annotation.min.js"></script>

  <script>
    document.addEventListener("DOMContentLoaded", function () {
      const stages = ["G1", "G2", "Prophase", "Metaphase", "Anaphase", "Telophase", "Daughter"];
      const rowKeys = ["G1", "G2", "pro", "meta", "ana", "telo", "mit-inter"];

      // Distinct properties for each metric to handle overlapping values visually
      const fields = [
        { key: "chrom", label: "Chromosomes", color: "#2563eb", dash: [5,7], pointStyle: 'circle', radius: 3 },
        { key: "chromatid", label: "Chromatids", color: "#16a34a", dash: [6, 6], pointStyle: 'triangle', radius: 6 },
        { key: "centromere", label: "Centromeres", color: "#d97706", dash: [2, 2], pointStyle: 'rectRot', radius: 6 },
        { key: "dna", label: "DNA Molecules", color: "#dc2626", dash: [10, 4], pointStyle: 'rect', radius: 5 }
      ];

      const humanPresetValues = {
        "G1":       { chrom: 46, chromatid: 46, centromere: 46, dna: 46 },
        "G2":       { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "pro":      { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "meta":     { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "ana":      { chrom: 92, chromatid: 92, centromere: 92, dna: 92 },
        "telo":     { chrom: 92, chromatid: 92, centromere: 92, dna: 92 },
        "mit-inter":{ chrom: 46, chromatid: 46, centromere: 46, dna: 46 }
      };

      const ctx = document.getElementById("ccLineChart").getContext("2d");
      
      const datasets = fields.map(f => ({
        label: f.label,
        data: new Array(rowKeys.length).fill(null),
        borderColor: f.color,
        backgroundColor: f.color,
        borderWidth: 2.5,
        borderDash: f.dash,
        pointStyle: f.pointStyle,
        pointRadius: f.radius,
        pointHoverRadius: 8,
        tension: 0.1,
        fill: false
      }));

      const chart = new Chart(ctx, {
        type: 'line',
        data: { labels: stages, datasets: datasets },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          interaction: {
            mode: 'index',
            intersect: false,
          },
          plugins: {
            legend: {
              position: 'top',
              labels: {
                usePointStyle: true,
                boxWidth: 8
              }
            },
            tooltip: {
              enabled: true,
              callbacks: {
                label: function(context) {
                  let label = context.dataset.label || '';
                  if (label) {
                    label += ': ';
                  }
                  if (context.parsed.y !== null) {
                    label += context.parsed.y;
                  }
                  return label;
                }
              }
            },
            annotation: {
              annotations: {
                dnaSynthesisLine: {
                  type: 'line',
                  xMin: 0.5,
                  xMax: 0.5,
                  borderColor: 'rgba(220, 38, 200, 0.5)',
                  borderWidth: 2,
                  borderDash: [4, 4],
                  label: {
                    display: true,
                    content: 'DNA Synthesis',
                    position: 'start',
                    backgroundColor: 'rgba(220, 38, 200, 0.8)',
                    font: { size: 10, weight: 'bold' },
                    padding: 4
                  }
                },
                cytokinesisLine: {
                  type: 'line',
                  xMin: 5.5,
                  xMax: 5.5,
                  borderColor: 'rgba(220, 38, 200, 0.5)',
                  borderWidth: 2,
                  borderDash: [4, 4],
                  label: {
                    display: true,
                    content: 'Cytokinesis',
                    position: 'start',
                    backgroundColor: 'rgba(220, 38, 200, 0.8)',
                    font: { size: 10, weight: 'bold' },
                    padding: 4
                  }
                }
              }
            }
          },
          scales: {
            y: { 
              beginAtZero: true, 
              ticks: { precision: 0 },
              grid: { color: 'rgba(0, 0, 0, 0.05)' }
            },
            x: {
              grid: { display: false }
            }
          }
        }
      });

      function updateChartData() {
        rowKeys.forEach((rowKey, rIndex) => {
          fields.forEach((field, fIndex) => {
            const input = document.querySelector(`.cc-wrapper input[data-row="${rowKey}"][data-field="${field.key}"]`);
            const val = input && input.value !== "" ? parseFloat(input.value) : null;
            chart.data.datasets[fIndex].data[rIndex] = val;
          });
        });
        chart.update();
      }

      document.querySelectorAll('.cc-wrapper input[type="number"]').forEach(input => {
        input.addEventListener('input', updateChartData);
      });

      document.getElementById('cc-btn-preset').addEventListener('click', function() {
        rowKeys.forEach(rowKey => {
          fields.forEach(field => {
            const input = document.querySelector(`.cc-wrapper input[data-row="${rowKey}"][data-field="${field.key}"]`);
            if (input) {
              input.value = humanPresetValues[rowKey][field.key];
            }
          });
        });
        updateChartData();
      });

      document.getElementById('cc-btn-clear').addEventListener('click', function() {
        document.querySelectorAll('.cc-wrapper input[type="number"]').forEach(input => {
          input.value = '';
        });
        updateChartData();
      });

      // Export Chart as Image feature
      document.getElementById('cc-btn-save').addEventListener('click', function() {
        const link = document.createElement('a');
        link.download = 'mitosis-chromosome-chart.png';
        link.href = chart.toBase64Image();
        link.click();
      });
    });
  </script>
</div>


<hr>

<div class="meio-wrapper">
  <style>
    .meio-wrapper {
      font-family: inherit;
      color: inherit;
      margin: 2rem 0;
      width: 100%;
    }
    .meio-wrapper table {
      width: 100% !important;
      border-collapse: collapse !important;
      margin-bottom: 1.5rem !important;
      font-size: 0.9rem;
    }
    .meio-wrapper th, .meio-wrapper td {
      padding: 8px 10px !important;
      text-align: center;
      border-bottom: 1px solid var(--global-divider-color);
    }
    .meio-wrapper th{
      color: var(--global-2nd-color);
    }
    .meio-wrapper th:first-child, .meio-wrapper td:first-child {
      text-align: left !important;
    }
    .meio-wrapper .meio-group-row td {
      font-weight: bold;
      background-color: var(--global-bg-color-2, rgba(0,0,0,0.03));
      text-align: left !important;
    }
    .meio-wrapper input[type="number"] {
      width: 65px !important;
      max-width: 100% !important;
      padding: 4px 6px !important;
      text-align: center;
      border: 1px solid var(--global-divider-color);
      border-radius: 4px;
      background: var(--global-bg-color);
      color: var(--global-text-color);
      box-sizing: border-box;
    }
    .meio-chart-container {
      position: relative;
      width: 100%;
      height: 320px;
      max-height: 400px;
      margin-top: 1rem;
    }
  </style>
  <h1>Meiosis</h1>
    <div class="meio-btn-group">
        <button type="button" id="meio-btn-preset" class="meio-btn">Load Human Germ Cell (2n = 46)</button>
        <button type="button" id="meio-btn-clear" class="meio-btn">Clear Table</button>
        <button type="button" id="meio-btn-save" class="meio-btn">📥 Save Chart Image</button>
    </div>
  <div style="overflow-x: auto;">
    <table id="meio-table">
      <thead>
        <tr>
          <th style="text-align:left;">Stage</th>
          <th># Chromosomes</th>
          <th># Chromatids</th>
          <th># Centromeres</th>
          <th># DNA Molecules</th>
        </tr>
      </thead>
      <tbody>
        <tr class="meio-group-row">
            <td colspan="5" style="color: var(--global-3rd-color)">Interphase</td>
        </tr>
        <tr>
          <td class="meio-stage">G1</td>
          <td><input type="number" min="0" data-row="meio-g1" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-g1" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-g1" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-g1" data-field="dna"></td>
        </tr>
                <tr>
          <td class="meio-stage">G2</td>
          <td><input type="number" min="0" data-row="meio-g2" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-g2" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-g2" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-g2" data-field="dna"></td>
        </tr>
        <tr class="meio-group-row">
            <td colspan="5" style="color: var(--global-3rd-color)">Meiosis I</td>
        </tr>
        <tr>
          <td class="meio-stage">Prophase I</td>
          <td><input type="number" min="0" data-row="meio-pro1" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-pro1" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-pro1" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-pro1" data-field="dna"></td>
        </tr>
        <tr>
          <td class="meio-stage">Metaphase I</td>
          <td><input type="number" min="0" data-row="meio-meta1" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-meta1" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-meta1" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-meta1" data-field="dna"></td>
        </tr>
        <tr>
          <td class="meio-stage">Anaphase I</td>
          <td><input type="number" min="0" data-row="meio-ana1" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-ana1" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-ana1" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-ana1" data-field="dna"></td>
        </tr>
        <tr>
          <td class="meio-stage">Telophase I</td>
          <td><input type="number" min="0" data-row="meio-telo1" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-telo1" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-telo1" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-telo1" data-field="dna"></td>
        </tr>
        <tr class="meio-group-row">
            <td colspan="5" style="color: var(--global-3rd-color)">Meiosis II</td>
        </tr>
        <tr>
          <td class="meio-stage">Prophase II</td>
          <td><input type="number" min="0" data-row="meio-pro2" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-pro2" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-pro2" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-pro2" data-field="dna"></td>
        </tr>
        <tr>
          <td class="meio-stage">Metaphase II</td>
          <td><input type="number" min="0" data-row="meio-meta2" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-meta2" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-meta2" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-meta2" data-field="dna"></td>
        </tr>
        <tr>
          <td class="meio-stage">Anaphase II</td>
          <td><input type="number" min="0" data-row="meio-ana2" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-ana2" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-ana2" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-ana2" data-field="dna"></td>
        </tr>
        <tr>
          <td class="meio-stage">Telophase II</td>
          <td><input type="number" min="0" data-row="meio-telo2" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-telo2" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-telo2" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-telo2" data-field="dna"></td>
        </tr>
        <tr class="meio-group-row">
            <td colspan="5" style="color: var(--global-3rd-color)">Post-Cytokinesis</td>
        </tr>
        <tr>
          <td class="meio-stage">Gamete</td>
          <td><input type="number" min="0" data-row="meio-gam" data-field="chrom"></td>
          <td><input type="number" min="0" data-row="meio-gam" data-field="chromatid"></td>
          <td><input type="number" min="0" data-row="meio-gam" data-field="centromere"></td>
          <td><input type="number" min="0" data-row="meio-gam" data-field="dna"></td>
        </tr>
      </tbody>
    </table>
  </div>
    <caption><h4 style="text-align: center">Genetic materials overtime in meiosis</h4></caption>
  <div class="meio-chart-container">
    <canvas id="meioLineChart"></canvas>
  </div>

  <script>
    document.addEventListener("DOMContentLoaded", function () {
      const meioStages = [
        "G1", "G2", "Prophase I", "Metaphase I", "Anaphase I", 
        "Telophase I", "Prophase II", "Metaphase II", "Anaphase II", "Telophase II",
        "Gamete"
      ];
      const meioRowKeys = [
        "meio-g1", "meio-g2", "meio-pro1", "meio-meta1", "meio-ana1", 
        "meio-telo1", "meio-pro2", "meio-meta2", "meio-ana2", "meio-telo2",
        "meio-gam"
      ];
      
      // Distinct properties for each metric to handle overlapping values visually
      const meioFields = [
        { key: "chrom", label: "Chromosomes", color: "#2563eb", dash: [5,7], pointStyle: 'circle', radius: 3 },
        { key: "chromatid", label: "Chromatids", color: "#16a34a", dash: [6, 6], pointStyle: 'triangle', radius: 6 },
        { key: "centromere", label: "Centromeres", color: "#d97706", dash: [2, 2], pointStyle: 'rectRot', radius: 6 },
        { key: "dna", label: "DNA Molecules", color: "#dc2626", dash: [10, 4], pointStyle: 'rect', radius: 5 }
      ];

      // Human Meiosis standard layout tracking contents per cell lineage
      const meioPresetValues = {
        "meio-g1":    { chrom: 46, chromatid: 46, centromere: 46, dna: 46 },
        "meio-g2":    { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "meio-pro1":  { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "meio-meta1": { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "meio-ana1":  { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "meio-telo1":  { chrom: 46, chromatid: 92, centromere: 46, dna: 92 },
        "meio-pro2":  { chrom: 23, chromatid: 46, centromere: 23, dna: 46 },
        "meio-meta2": { chrom: 23, chromatid: 46, centromere: 23, dna: 46 },
        "meio-ana2":  { chrom: 46, chromatid: 46, centromere: 46, dna: 46 },
        "meio-telo2":  { chrom: 46, chromatid: 46, centromere: 46, dna: 46 },
        "meio-gam": { chrom: 23, chromatid: 23, centromere: 23, dna: 23 }
      };

      const meioCtx = document.getElementById("meioLineChart").getContext("2d");
      
      const meioDatasets = meioFields.map(f => ({
        label: f.label,
        data: new Array(meioRowKeys.length).fill(null),
        borderColor: f.color,
        backgroundColor: f.color,
        borderWidth: 2.5,
        borderDash: f.dash,
        pointStyle: f.pointStyle,
        pointRadius: f.radius,
        pointHoverRadius: 8,
        tension: 0.1,
        fill: false
      }));

      const meioChart = new Chart(meioCtx, {
        type: 'line',
        data: { labels: meioStages, datasets: meioDatasets },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          interaction: {
            mode: 'index',
            intersect: false,
          },
          plugins: {
            legend: {
              position: 'top',
              labels: {
                usePointStyle: true,
                boxWidth: 8
              }
            },
            tooltip: {
              enabled: true
            },
            annotation: {
              annotations: {
                dnaSynthesisLine: {
                  type: 'line',
                  xMin: 0.5,
                  xMax: 0.5,
                  borderColor: 'rgba(220, 38, 200, 0.5)',
                  borderWidth: 2,
                  borderDash: [4, 4],
                  label: {
                    display: true,
                    content: 'DNA Synthesis',
                    position: 'start',
                    backgroundColor: 'rgba(220, 38, 200, 0.8)',
                    font: { size: 10, weight: 'bold' },
                    padding: 4
                  }
                },
                cytokinesisLine1: {
                  type: 'line',
                  xMin: 5.5,
                  xMax: 5.5,
                  borderColor: 'rgba(220, 38, 200, 0.5)',
                  borderWidth: 2,
                  borderDash: [4, 4],
                  label: {
                    display: true,
                    content: 'Cytokinesis I',
                    position: 'start',
                    backgroundColor: 'rgba(220, 38, 200, 0.8)',
                    font: { size: 10, weight: 'bold' },
                    padding: 4
                  }
                },
                cytokinesisLine2: {
                  type: 'line',
                  xMin: 9.5,
                  xMax: 9.5,
                  borderColor: 'rgba(220, 38, 200, 0.5)',
                  borderWidth: 2,
                  borderDash: [4, 4],
                  label: {
                    display: true,
                    content: 'Cytokinesis II',
                    position: 'start',
                    backgroundColor: 'rgba(220, 38, 200, 0.8)',
                    font: { size: 10, weight: 'bold' },
                    padding: 4
                  }
                }
              }
            }
          },
          scales: {
            y: { 
              beginAtZero: true, 
              ticks: { precision: 0 },
              grid: { color: 'rgba(0, 0, 0, 0.05)' }
            },
            x: {
              grid: { display: false }
            }
          }
        }
      });

      function updateMeioChartData() {
        meioRowKeys.forEach((rowKey, rIndex) => {
          meioFields.forEach((field, fIndex) => {
            const input = document.querySelector(`.meio-wrapper input[data-row="${rowKey}"][data-field="${field.key}"]`);
            const val = input && input.value !== "" ? parseFloat(input.value) : null;
            meioChart.data.datasets[fIndex].data[rIndex] = val;
          });
        });
        meioChart.update();
      }

      document.querySelectorAll('.meio-wrapper input[type="number"]').forEach(input => {
        input.addEventListener('input', updateMeioChartData);
      });

      document.getElementById('meio-btn-preset').addEventListener('click', function() {
        meioRowKeys.forEach(rowKey => {
          meioFields.forEach(field => {
            const input = document.querySelector(`.meio-wrapper input[data-row="${rowKey}"][data-field="${field.key}"]`);
            if (input) {
              input.value = meioPresetValues[rowKey][field.key];
            }
          });
        });
        updateMeioChartData();
      });

      document.getElementById('meio-btn-clear').addEventListener('click', function() {
        document.querySelectorAll('.meio-wrapper input[type="number"]').forEach(input => {
          input.value = '';
        });
        updateMeioChartData();
      });

      // Export Chart as Image feature
      document.getElementById('meio-btn-save').addEventListener('click', function() {
        const link = document.createElement('a');
        link.download = 'meiosis-chromosome-chart.png';
        link.href = meioChart.toBase64Image();
        link.click();
      });
    });
  </script>
</div>