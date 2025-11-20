<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Cybersecurity Framework — Interactive Graph</title>

  <!-- D3 (v7) CDN -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/d3/7.8.5/d3.min.js" integrity="sha512-rZf6d3q0o6oB0Q8oMCR4GQ4kZk1c/5mQ6q5H9pA5r8Kp1z6e3mH2lwjxQq0oZx0cGeRr0bF1F4w9JqQw7rN2w==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

  <style>
    :root{
      --bg:#0f1724;
      --panel:#0b1220;
      --muted:#9aa6b2;
      --accent:#f6b042;
      --node-bg:#0b2a3a;
      --node-stroke:#173b4a;
      --card-bg: rgba(255,255,255,0.03);
    }

    html,body{
      height:100%;
      margin:0;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg, #071125 0%, #071225 100%);
      color:#e6eef6;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    header{
      padding:18px 28px;
      display:flex;
      gap:12px;
      align-items:center;
      border-bottom:1px solid rgba(255,255,255,0.04);
      background: linear-gradient(90deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));
    }
    header h1{
      font-size:18px;
      margin:0;
      letter-spacing:0.2px;
      font-weight:600;
    }
    header p{ margin:0; color:var(--muted); font-size:13px }

    main { padding:18px; display:block; }

    .chart-wrap{
      background: var(--card-bg);
      border-radius:12px;
      padding:14px;
      box-shadow: 0 6px 18px rgba(3,10,18,0.6);
      border:1px solid rgba(255,255,255,0.03);
      max-width:1200px;
      margin: 12px auto;
    }

    /* svg container */
    #chart {
      width:100%;
      height:600px;
      touch-action: none;
    }

    .node rect {
      fill: var(--node-bg);
      stroke: var(--node-stroke);
      stroke-width:1.2px;
      rx:8;
      ry:8;
    }

    .node text {
      font-size:12px;
      fill:#e6eef6;
      pointer-events:none;
    }

    .link {
      fill: none;
      stroke: rgba(255,255,255,0.08);
      stroke-width:1.6px;
    }

    .tooltip {
      position: absolute;
      background: rgba(10,16,24,0.95);
      color: #d9f0ff;
      border-radius: 8px;
      padding:8px 10px;
      font-size:13px;
      pointer-events:none;
      box-shadow: 0 6px 20px rgba(3,10,18,0.6);
      border:1px solid rgba(255,255,255,0.03);
      max-width:300px;
      line-height:1.3;
    }

    .controls {
      display:flex;
      gap:10px;
      align-items:center;
      margin-bottom:8px;
      flex-wrap:wrap;
    }

    .btn {
      background:transparent;
      color:var(--muted);
      border:1px solid rgba(255,255,255,0.04);
      padding:6px 10px;
      border-radius:8px;
      cursor:pointer;
      font-size:13px;
    }
    .btn:active{ transform:translateY(1px) }

    footer {
      color:var(--muted);
      font-size:13px;
      text-align:center;
      margin-top:10px;
    }

    /* fallback plain list for no-js */
    .no-js-list {
      display:none;
      background: #071226;
      padding:12px;
      border-radius:8px;
      margin-top:12px;
      color:var(--muted);
      font-size:14px;
    }
    .no-js-list pre{ white-space:pre-wrap; }
    @media (max-width:700px){
      #chart { height:520px; }
      .node text{ font-size:11px; }
    }
  </style>
</head>
<body>

  <header>
    <div>
      <h1>Cybersecurity Framework — Interactive Graph</h1>
      <p>Click nodes to expand/collapse. Use for portfolio or GitHub Pages.</p>
    </div>
  </header>

  <main>
    <div class="chart-wrap">
      <div class="controls" aria-hidden="false">
        <button id="expandAll" class="btn">Expand all</button>
        <button id="collapseAll" class="btn">Collapse all</button>
        <button id="resetView" class="btn">Reset view</button>
      </div>

      <div id="chart" role="img" aria-label="Interactive tree of cybersecurity functions and controls"></div>
      <div id="tooltip" class="tooltip" style="display:none;"></div>

      <div class="no-js-list" id="nojs">
<pre>
#### 1. Identify
- Asset Management
- Business Environment Analysis
- Governance
- Risk Assessment
- Risk Management Strategy

#### 2. Protect
- Access Control
- Awareness and Training
- Data Security
- Information Protection
- Protective Technology
- Maintenance

#### 3. Detect
- Anomalies and Events
- Security Continuous Monitoring
- Detection Processes

#### 4. Respond
- Response Planning
- Communications
- Analysis
- Mitigation
- Improvements

#### 5. Recover
- Recovery Planning
- Improvements
- Communications
</pre>
      </div>
    </div>

    <footer>
      Tip: you can screenshot or export this view for your portfolio. Licensed for personal and educational use.
    </footer>
  </main>

<script>
/* ---------- Data (from your list) ---------- */
const data = {
  "name": "Cybersecurity Framework",
  "children": [
    {
      "name": "Identify",
      "children": [
        {"name": "Asset Management"},
        {"name": "Business Environment Analysis"},
        {"name": "Governance"},
        {"name": "Risk Assessment"},
        {"name": "Risk Management Strategy"}
      ]
    },
    {
      "name": "Protect",
      "children": [
        {"name": "Access Control"},
        {"name": "Awareness and Training"},
        {"name": "Data Security"},
        {"name": "Information Protection"},
        {"name": "Protective Technology"},
        {"name": "Maintenance"}
      ]
    },
    {
      "name": "Detect",
      "children": [
        {"name": "Anomalies and Events"},
        {"name": "Security Continuous Monitoring"},
        {"name": "Detection Processes"}
      ]
    },
    {
      "name": "Respond",
      "children": [
        {"name": "Response Planning"},
        {"name": "Communications"},
        {"name": "Analysis"},
        {"name": "Mitigation"},
        {"name": "Improvements"}
      ]
    },
    {
      "name": "Recover",
      "children": [
        {"name": "Recovery Planning"},
        {"name": "Improvements"},
        {"name": "Communications"}
      ]
    }
  ]
};

/* ---------- Setup SVG and layout ---------- */
const container = document.getElementById('chart');
const tooltip = document.getElementById('tooltip');

let width = container.clientWidth;
let height = container.clientHeight;

const svg = d3.select(container)
  .append('svg')
  .attr('width', '100%')
  .attr('height', '100%')
  .attr('viewBox', [0, 0, width, height].join(' '))
  .style('overflow', 'visible');

const g = svg.append('g').attr('transform', `translate(40,40)`);

let root = d3.hierarchy(data);
const tree = d3.tree().nodeSize([160, 120]); // adjusts spacing

// initialize collapse (collapse all children of root's children)
root.children.forEach(d => {
  if(d.children) {
    d._children = d.children;
    d.children = null;
  }
});

update(root);

/* ---------- Update function ---------- */
function update(source) {
  // recompute dimensions
  width = container.clientWidth;
  height = container.clientHeight;
  svg.attr('viewBox', [0, 0, width, height].join(' '));

  tree.size([width - 160, height - 120]);
  tree(root);

  // links
  const links = g.selectAll('.link')
    .data(root.links(), d => d.target.data.name + '-' + (d.target.depth));

  links.join(
    enter => enter.append('path')
                  .attr('class','link')
                  .attr('d', d => diagonal(d)),
    update => update.attr('d', d => diagonal(d)),
    exit => exit.remove()
  );

  // nodes
  const nodes = g.selectAll('.node')
    .data(root.descendants(), d => d.data.name + '-' + d.depth);

  const nodeEnter = nodes.enter()
    .append('g')
    .attr('class','node')
    .attr('transform', d => `translate(${d.x},${d.y})`)
    .style('cursor', 'pointer')
    .on('click', (event,d) => {
      toggle(d);
      update(d);
    })
    .on('mouseover', (event,d) => {
      tooltip.style.display = 'block';
      tooltip.innerHTML = `<strong>${d.data.name}</strong><br/><small>Level: ${d.depth}</small>`;
    })
    .on('mousemove', (event) => {
      tooltip.style.left = (event.pageX + 14) + 'px';
      tooltip.style.top = (event.pageY + 10) + 'px';
    })
    .on('mouseout', () => {
      tooltip.style.display = 'none';
    });

  nodeEnter.append('rect')
    .attr('x', -70)
    .attr('y', -18)
    .attr('width', 140)
    .attr('height', 36);

  nodeEnter.append('text')
    .attr('dy', '0.32em')
    .attr('text-anchor', 'middle')
    .text(d => d.data.name)
    .call(wrap, 120);

  // update positions of all nodes
  const nodeUpdate = nodeEnter.merge(nodes);
  nodeUpdate.transition().duration(300)
    .attr('transform', d => `translate(${d.x},${d.y})`);

  // remove old nodes
  nodes.exit().remove();

  // reposition container group to center top-level nodes nicer
  // (optional visual tweak)
  const topPadding = 20;
  const xOffset = 0;
  const yOffset = topPadding;
  g.attr('transform', `translate(${xOffset + 40},${yOffset + 40})`);
}

/* ---------- Utility functions ---------- */
function diagonal(d) {
  // curved path
  const sx = d.source.x;
  const sy = d.source.y + 18;
  const tx = d.target.x;
  const ty = d.target.y - 18;
  return `M${sx},${sy} C${sx},${(sy+ty)/2} ${tx},${(sy+ty)/2} ${tx},${ty}`;
}

function toggle(d) {
  if (d.children) {
    d._children = d.children;
    d.children = null;
  } else {
    d.children = d._children;
    d._children = null;
  }
}

function wrap(text, width) {
  // wrap long names onto multiple lines inside rect
  text.each(function() {
    var text = d3.select(this),
        words = text.text().split(/\s+/).reverse(),
        line = [],
        lineNumber = 0,
        lineHeight = 1.1, // ems
        y = text.attr("y"),
        dy = 0,
        tspan = text.text(null).append("tspan").attr("x", 0).attr("y", 0).attr("dy", dy + "em");
    var word;
    while (word = words.pop()) {
      line.push(word);
      tspan.text(line.join(" "));
      if (tspan.node().getComputedTextLength() > width) {
        line.pop();
        tspan.text(line.join(" "));
        line = [word];
        tspan = text.append("tspan").attr("x", 0).attr("y", 0).attr("dy", ++lineNumber * lineHeight + dy + "em").text(word);
      }
    }
  });
}

/* ---------- Controls ---------- */
document.getElementById('expandAll').addEventListener('click', () => {
  expandAll(root);
  update(root);
});
document.getElementById('collapseAll').addEventListener('click', () => {
  root.children.forEach(d => {
    if (d.children) { d._children = d.children; d.children = null; }
  });
  update(root);
});
document.getElementById('resetView').addEventListener('click', () => {
  // collapse all children of root's children again
  root.children.forEach(d => {
    if (d.children) { d._children = d.children; d.children = null; }
  });
  update(root);
});

function expandAll(node) {
  if (node._children) {
    node.children = node._children;
    node._children = null;
  }
  if (node.children) {
    node.children.forEach(expandAll);
  }
}

/* ---------- Resize handling ---------- */
window.addEventListener('resize', () => {
  update(root);
});

/* ---------- No-JS fallback visibility ---------- */
document.getElementById('nojs').style.display = 'none';
</script>

<!-- Show no-js content if JS disabled -->
<noscript>
  <style>.no-js-list{display:block}</style>
</noscript>
</body>
</html>
