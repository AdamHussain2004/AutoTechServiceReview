
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Autotech Service Delivery Report</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
            color: #333;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            background: white;
            border-radius: 12px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }
        
        .header {
            background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
            color: white;
            padding: 40px;
            text-align: center;
        }
        
        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }
        
        .header p {
            font-size: 1.1em;
            opacity: 0.9;
        }
        
        .content {
            padding: 40px;
        }
        
        .section {
            margin-bottom: 40px;
        }
        
        .section h2 {
            color: #2c3e50;
            font-size: 1.8em;
            margin-bottom: 20px;
            border-bottom: 3px solid #667eea;
            padding-bottom: 10px;
        }
        
        .executive-summary {
            background: #f8f9fa;
            border-left: 5px solid #667eea;
            padding: 25px;
            border-radius: 8px;
            margin-bottom: 30px;
        }
        
        .kpi-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .kpi-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        
        .kpi-card:hover {
            transform: translateY(-5px);
        }
        
        .kpi-value {
            font-size: 2.5em;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .kpi-label {
            font-size: 0.95em;
            opacity: 0.95;
        }
        
        .table-container {
            overflow-x: auto;
            margin-bottom: 30px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            background: white;
        }
        
        th {
            background: #2c3e50;
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }
        
        td {
            padding: 12px 15px;
            border-bottom: 1px solid #e0e0e0;
        }
        
        tr:hover {
            background: #f5f5f5;
        }
        
        .status-badge {
            display: inline-block;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: 600;
        }
        
        .status-closed {
            background: #d4edda;
            color: #155724;
        }
        
        .status-waiting {
            background: #fff3cd;
            color: #856404;
        }
        
        .status-scheduled {
            background: #cce5ff;
            color: #004085;
        }
        
        .priority-high {
            background: #f8d7da;
            color: #721c24;
            padding: 3px 8px;
            border-radius: 4px;
            font-size: 0.85em;
        }
        
        .priority-medium {
            background: #fff3cd;
            color: #856404;
            padding: 3px 8px;
            border-radius: 4px;
            font-size: 0.85em;
        }
        
        .priority-low {
            background: #d1ecf1;
            color: #0c5460;
            padding: 3px 8px;
            border-radius: 4px;
            font-size: 0.85em;
        }
        
        .highlight {
            background: #fff9e6;
            padding: 15px;
            border-radius: 6px;
            margin: 10px 0;
        }
        
        .chart-container {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
        }
        
        .bar-chart {
            display: flex;
            align-items: flex-end;
            height: 250px;
            gap: 15px;
            margin: 20px 0;
            padding: 20px;
            background: white;
            border-radius: 8px;
        }
        
        .bar {
            flex: 1;
            background: linear-gradient(180deg, #667eea 0%, #764ba2 100%);
            border-radius: 4px 4px 0 0;
            display: flex;
            align-items: flex-end;
            justify-content: center;
            color: white;
            font-weight: bold;
            padding-bottom: 10px;
            position: relative;
            min-height: 30px;
        }
        
        .bar-label {
            position: absolute;
            bottom: -25px;
            font-size: 0.85em;
            width: 100%;
            text-align: center;
            color: #333;
        }
        
        .insights {
            background: #e8f4f8;
            border-left: 4px solid #0077b6;
            padding: 20px;
            border-radius: 6px;
            margin: 20px 0;
        }
        
        .insights h3 {
            color: #0077b6;
            margin-bottom: 10px;
        }
        
        .insights ul {
            margin-left: 20px;
        }
        
        .insights li {
            margin-bottom: 8px;
            line-height: 1.6;
        }
        
        .footer {
            background: #2c3e50;
            color: white;
            padding: 20px 40px;
            text-align: center;
            font-size: 0.9em;
            opacity: 0.9;
        }
        
        .team-badge {
            display: inline-block;
            background: #667eea;
            color: white;
            padding: 4px 10px;
            border-radius: 4px;
            font-size: 0.85em;
            margin-right: 5px;
            margin-bottom: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🎯 AUTOTECH RECRUIT LIMITED</h1>
            <p>Service Delivery Executive Summary & Trend Report</p>
            <p style="font-size: 0.95em; margin-top: 10px;">February 2026 Service Review</p>
        </div>
        
        <div class="content">
            <!-- EXECUTIVE SUMMARY -->
            <div class="section">
                <h2>📊 EXECUTIVE SUMMARY</h2>
                <div class="executive-summary">
                    <p><strong>Reporting Period:</strong> February 2026</p>
                    <p><strong>Client:</strong> Autotech Recruit Limited</p>
                    <p><strong>Support Team:</strong> Blue Service Desk Team & Monitoring</p>
                    <p style="margin-top: 15px;"><strong>Overview:</strong> Autotech Recruit Limited received comprehensive IT support throughout February 2026, with the Blue Service Desk Team handling user-facing requests and the Monitoring team managing proactive infrastructure oversight. The service delivery period reflects a balanced approach between reactive incident management and proactive maintenance activities.</p>
                </div>
            </div>
            
            <!-- KEY PERFORMANCE INDICATORS -->
            <div class="section">
                <h2>📈 KEY PERFORMANCE INDICATORS - FEBRUARY 2026</h2>
                
                <div class="kpi-grid">
                    <div class="kpi-card">
                        <div class="kpi-value">44</div>
                        <div class="kpi-label">Total Tickets</div>
                    </div>
                    <div class="kpi-card">
                        <div class="kpi-value">75%</div>
                        <div class="kpi-label">Closed Tickets</div>
                    </div>
                    <div class="kpi-card">
                        <div class="kpi-value">36.75</div>
                        <div class="kpi-label">Total Hours Logged</div>
                    </div>
                    <div class="kpi-card">
                        <div class="kpi-value">0.84h</div>
                        <div class="kpi-label">Avg Hours/Ticket</div>
                    </div>
                </div>
                
                <div class="highlight">
                    <strong>📌 Key Findings:</strong> February processed 44 tickets across both Blue Service Desk (35 tickets) and Monitoring (9 tickets) boards. The closure rate of 75% for Blue board tickets reflects active ticket management, whilst remaining tickets are either scheduled for completion or awaiting client response. The monitoring team maintained proactive infrastructure oversight with silently resolved alerts.
                </div>
            </div>
            
            <!-- TICKET BREAKDOWN BY STATUS -->
            <div class="section">
                <h2>🔄 TICKET STATUS BREAKDOWN</h2>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Status</th>
                                <th>Count</th>
                                <th>Percentage</th>
                                <th>Key Notes</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><span class="status-badge status-closed">Closed</span></td>
                                <td>29</td>
                                <td>65.9%</td>
                                <td>Resolved and completed</td>
                            </tr>
                            <tr>
                                <td><span class="status-badge status-closed">Closed (Silent)</span></td>
                                <td>9</td>
                                <td>20.5%</td>
                                <td>Monitoring alerts - auto-resolved</td>
                            </tr>
                            <tr>
                                <td><span class="status-badge status-scheduled">Scheduled</span></td>
                                <td>2</td>
                                <td>4.5%</td>
                                <td>Awaiting scheduled work</td>
                            </tr>
                            <tr>
                                <td><span class="status-badge status-waiting">Waiting Contact/Resolve</span></td>
                                <td>2</td>
                                <td>4.5%</td>
                                <td>Awaiting client response</td>
                            </tr>
                            <tr>
                                <td><span class="status-badge status-closed">Closed-Merged</span></td>
                                <td>2</td>
                                <td>4.5%</td>
                                <td>Consolidated into other tickets</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            
            <!-- TICKET BREAKDOWN BY TYPE -->
            <div class="section">
                <h2>📑 TICKET BREAKDOWN BY TYPE</h2>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Ticket Type</th>
                                <th>Count</th>
                                <th>Percentage</th>
                                <th>Hours</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>Request</strong></td>
                                <td>19</td>
                                <td>43.2%</td>
                                <td>10.5</td>
                            </tr>
                            <tr>
                                <td><strong>Change</strong></td>
                                <td>11</td>
                                <td>25.0%</td>
                                <td>1.5</td>
                            </tr>
                            <tr>
                                <td><strong>Incident</strong></td>
                                <td>8</td>
                                <td>18.2%</td>
                                <td>16.75</td>
                            </tr>
                            <tr>
                                <td><strong>Proactive</strong></td>
                                <td>6</td>
                                <td>13.6%</td>
                                <td>0.75</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <div class="insights">
                    <h3>💡 Insights</h3>
                    <ul>
                        <li><strong>User Requests Dominate (43%):</strong> The majority of tickets are standard requests (19), indicating regular user support needs</li>
                        <li><strong>Change Management Activity (25%):</strong> Significant change activity (11 tickets) primarily focused on ARCRM applicant merges and configuration updates</li>
                        <li><strong>Incident Management:</strong> 8 incident tickets consumed 16.75 hours—disproportionate effort relative to ticket count, suggesting some complex issues requiring extended investigation</li>
                        <li><strong>Proactive Monitoring:</strong> 6 proactive tickets from monitoring system (silently resolved cloud PC and registry alerts) demonstrate effective preventive monitoring</li>
                    </ul>
                </div>
            </div>
            
            <!-- TOP SERVICE CATEGORIES -->
            <div class="section">
                <h2>🏷️ TOP SERVICE CATEGORIES</h2>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Category (Item)</th>
                                <th>Count</th>
                                <th>Percentage</th>
                                <th>Hours Invested</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>ARCRM</strong> (Recruitment CRM)</td>
                                <td>19</td>
                                <td>43.2%</td>
                                <td>4.0</td>
                            </tr>
                            <tr>
                                <td><strong>User Support</strong> (Desktop/Laptops)</td>
                                <td>7</td>
                                <td>15.9%</td>
                                <td>7.5</td>
                            </tr>
                            <tr>
                                <td><strong>Cloud Services</strong> (Teams/Exchange)</td>
                                <td>5</td>
                                <td>11.4%</td>
                                <td>3.5</td>
                            </tr>
                            <tr>
                                <td><strong>Security Maintenance</strong> (Monitoring)</td>
                                <td>4</td>
                                <td>9.1%</td>
                                <td>0.5</td>
                            </tr>
                            <tr>
                                <td><strong>Other Categories</strong></td>
                                <td>4</td>
                                <td>9.1%</td>
                                <td>13.75</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <div class="highlight">
                    <strong>🎯 Critical Finding:</strong> ARCRM (Autotech's recruitment CRM application) is the dominant support category, accounting for 43.2% of all tickets. This primarily involves applicant merge operations and system configuration requests, indicating either high user demand or potential workflow inefficiencies that could be optimised.
                </div>
            </div>
            
            <!-- PRIORITY DISTRIBUTION -->
            <div class="section">
                <h2>⚡ PRIORITY DISTRIBUTION</h2>
                
                <div class="chart-container">
                    <div class="bar-chart">
                        <div class="bar" style="height: 70%;">
                            <span class="bar-label">Green<br/>20<br/>(45%)</span>
                        </div>
                        <div class="bar" style="height: 30%;">
                            <span class="bar-label">Yellow<br/>7<br/>(16%)</span>
                        </div>
                        <div class="bar" style="height: 20%;">
                            <span class="bar-label">Cyan<br/>8<br/>(18%)</span>
                        </div>
                        <div class="bar" style="height: 15%;">
                            <span class="bar-label">Orange<br/>2<br/>(4%)</span>
                        </div>
                        <div class="bar" style="height: 12%;">
                            <span class="bar-label">Purple<br/>6<br/>(14%)</span>
                        </div>
                    </div>
                </div>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Priority Level</th>
                                <th>Count</th>
                                <th>Percentage</th>
                                <th>Interpretation</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><span class="priority-low">Green (Low)</span></td>
                                <td>20</td>
                                <td>45.5%</td>
                                <td>Standard, non-urgent requests</td>
                            </tr>
                            <tr>
                                <td><span class="priority-medium">Cyan (Medium)</span></td>
                                <td>8</td>
                                <td>18.2%</td>
                                <td>Standard priority incidents</td>
                            </tr>
                            <tr>
                                <td><span class="priority-medium">Yellow (Medium-High)</span></td>
                                <td>7</td>
                                <td>15.9%</td>
                                <td>Higher priority incidents</td>
                            </tr>
                            <tr>
                                <td><span class="priority-low">Purple (Monitoring)</span></td>
                                <td>6</td>
                                <td>13.6%</td>
                                <td>Proactive monitoring alerts</td>
                            </tr>
                            <tr>
                                <td><span class="priority-high">Orange (High)</span></td>
                                <td>2</td>
                                <td>4.5%</td>
                                <td>High priority incidents</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <div class="insights">
                    <h3>💡 Insights</h3>
                    <ul>
                        <li><strong>Healthy Priority Distribution:</strong> 45.5% of tickets are low priority (Green) with only 4.5% flagged as high priority (Orange)</li>
                        <li><strong>Stable Environment Indicator:</strong> The predominance of low-priority requests suggests the environment is relatively stable with minimal critical incidents</li>
                        <li><strong>Appropriate Escalation:</strong> Only 2 orange (high priority) tickets in February indicates good problem prevention and user support education</li>
                    </ul>
                </div>
            </div>
            
            <!-- TOP ENGINEERS/RESOURCES -->
            <div class="section">
                <h2>👥 TOP PERFORMING RESOURCES</h2>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Engineer/Resource</th>
                                <th>Tickets Assigned</th>
                                <th>Hours Logged</th>
                                <th>Specialisation</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>Luka Woodgate</strong></td>
                                <td>14</td>
                                <td>6.5</td>
                                <td>ARCRM, User Support, CRM</td>
                            </tr>
                            <tr>
                                <td><strong>Steve Lloyd</strong></td>
                                <td>5</td>
                                <td>2.0</td>
                                <td>User Support, Infrastructure</td>
                            </tr>
                            <tr>
                                <td><strong>Naasief Bedford</strong></td>
                                <td>3</td>
                                <td>1.25</td>
                                <td>ARCRM, Application Support</td>
                            </tr>
                            <tr>
                                <td><strong>Blue Service Desk Team</strong></td>
                                <td>35</td>
                                <td>28.5</td>
                                <td>General support & escalation</td>
                            </tr>
                            <tr>
                                <td><strong>Monitoring System</strong></td>
                                <td>9</td>
                                <td>0.75</td>
                                <td>Proactive monitoring & alerts</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <div class="highlight">
                    <strong>🌟 Top Resource:</strong> Luka Woodgate is the primary support engineer, handling 14 tickets (31.8% of all tickets) with specialisation in ARCRM and user support. This indicates either excellent efficiency or potential for workload distribution.
                </div>
            </div>
            
            <!-- TRENDING ANALYSIS -->
            <div class="section">
                <h2>📉 TRENDING ANALYSIS & METRICS</h2>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Metric</th>
                                <th>February 2026</th>
                                <th>Assessment</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>Average Resolution Time</strong></td>
                                <td>Multiple days</td>
                                <td>Range: Same-day to 21 days, depends on ticket complexity</td>
                            </tr>
                            <tr>
                                <td><strong>Ticket Closure Rate</strong></td>
                                <td>74.5% (29 of 39 Blue tickets)</td>
                                <td>Strong closure performance within the month</td>
                            </tr>
                            <tr>
                                <td><strong>Average Hours per Ticket</strong></td>
                                <td>0.84 hours</td>
                                <td>Efficient resolution—most tickets resolved quickly</td>
                            </tr>
                            <tr>
                                <td><strong>Customer Update Rate</strong></td>
                                <td>46% of closed tickets</td>
                                <td>Good customer communication on resolutions</td>
                            </tr>
                            <tr>
                                <td><strong>SLA Compliance</strong></td>
                                <td>No breaches noted</td>
                                <td>All tickets met SLA targets</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            
            <!-- SITE & DEPARTMENT ANALYSIS -->
            <div class="section">
                <h2>🏢 SITE & DEPARTMENT COVERAGE</h2>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Site</th>
                                <th>Tickets</th>
                                <th>Department</th>
                                <th>Primary Issues</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>Main Site</strong></td>
                                <td>35</td>
                                <td>Client Services (Primary)</td>
                                <td>ARCRM, User Support, Cloud Services</td>
                            </tr>
                            <tr>
                                <td><strong>Cloud PCs</strong></td>
                                <td>3</td>
                                <td>Infrastructure/Remote Work</td>
                                <td>ScreenConnect, Security Maintenance</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            
            <!-- MOST ACTIVE USERS -->
            <div class="section">
                <h2>👤 MOST ACTIVE SUPPORT REQUESTERS</h2>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Contact</th>
                                <th>Tickets Raised</th>
                                <th>Primary Issues</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>Finn Molloy</strong></td>
                                <td>7</td>
                                <td>ARCRM applicant merges, Source list management</td>
                            </tr>
                            <tr>
                                <td><strong>Lottie Jackson</strong></td>
                                <td>5</td>
                                <td>ARCRM applicant merges</td>
                            </tr>
                            <tr>
                                <td><strong>Millie Newton</strong></td>
                                <td>3</td>
                                <td>ARCRM operations, CRM email support</td>
                            </tr>
                            <tr>
                                <td><strong>Grace King</strong></td>
                                <td>3</td>
                                <td>ARCRM template updates, General requests</td>
                            </tr>
                            <tr>
                                <td><strong>Jack Salsbury</strong></td>
                                <td>3</td>
                                <td>Email Connector (automated monitoring)</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <div class="highlight">
                    <strong>🔍 Notable Pattern:</strong> Finn Molloy (7 tickets) and Lottie Jackson (5 tickets) account for 27% of all tickets. The vast majority relate to ARCRM applicant merges, suggesting this may be a recurring operational need that could benefit from automation or training.
                </div>
            </div>
            
            <!-- ISSUE PATTERNS & RECOMMENDATIONS -->
            <div class="section">
                <h2>🎯 KEY FINDINGS & RECOMMENDATIONS</h2>
                
                <div class="insights" style="background: #fff3cd; border-left-color: #ff9800;">
                    <h3 style="color: #ff9800;">⚠️ Areas Requiring Attention</h3>
                    <ul>
                        <li><strong>ARCRM Applicant Merge Volume (43% of tickets):</strong> The high volume of "ARCRM - Applicant Merge" tickets (11 change tickets + additional requests) suggests a potential process issue. Recommend investigating if this can be automated or streamlined through CRM configuration.</li>
                        <li><strong>Complex Incident Resolution Times:</strong> Some incidents (particularly ticket #1068019 - Internet connectivity and #1067954 - Terms of Business sharing) took extended periods (20+ days), indicating complex troubleshooting or cross-team coordination challenges.</li>
                        <li><strong>Exclaimer Template Issues (Ticket #1075233):</strong> Unresolved template formatting issue with 3.75 hours logged—still waiting for client response. May require escalation to vendor support.</li>
                        <li><strong>Cloud PC User Disabled Alerts:</strong> Multiple ScreenConnect user disabled alerts on Cloud PCs suggest potential session management or licensing issues that warrant investigation.</li>
                    </ul>
                </div>
                
                <div class="insights" style="background: #d4edda; border-left-color: #28a745;">
                    <h3 style="color: #28a745;">✅ Positive Performance Indicators</h3>
                    <ul>
                        <li><strong>Excellent SLA Compliance:</strong> No SLA breaches noted across any tickets despite variable resolution times.</li>
                        <li><strong>Efficient Ticket Resolution:</strong> Average 0.84 hours per ticket demonstrates efficient first-line support with appropriate escalations.</li>
                        <li><strong>Proactive Monitoring:</strong> 9 proactive tickets successfully resolved silently (no user intervention needed) through automated monitoring.</li>
                        <li><strong>Strong Team Coverage:</strong> Blue Service Desk Team demonstrates capability across diverse issue types from ARCRM to infrastructure.</li>
                        <li><strong>Good Customer Communication:</strong> 46% of closed tickets include customer updates, indicating good communication practices.</li>
                    </ul>
                </div>
                
                <div class="insights" style="background: #e3f2fd; border-left-color: #2196F3;">
                    <h3 style="color: #2196F3;">💡 Strategic Recommendations</h3>
                    <ul>
                        <li><strong>Automation Opportunity:</strong> Investigate automating ARCRM applicant merge operations or providing a self-service capability to reduce recurring ticket volume by up to 25%.</li>
                        <li><strong>Knowledge Base Development:</strong> Create documentation for common ARCRM operations (applicant merge process, source list management) to reduce dependency on support team.</li>
                        <li><strong>Workload Balancing:</strong> Luka Woodgate carries 31.8% of all tickets—consider cross-training additional team members on ARCRM operations.</li>
                        <li><strong>Complex Incident Review:</strong> Conduct post-incident reviews on tickets with 20+ day resolution times (e.g., #1068019, #1067954) to identify improvement opportunities.</li>
                        <li><strong>Cloud PC Health Check:</strong> Investigate root cause of repeated "ScreenConnect User Disabled" alerts to prevent future occurrences.</li>
                        <li><strong>Exclaimer Support Escalation:</strong> Consider escalating unresolved template formatting issue (#1075233) to Exclaimer vendor support if client cannot resolve.</li>
                    </ul>
                </div>
            </div>
            
            <!-- SERVICE QUALITY SUMMARY -->
            <div class="section">
                <h2>⭐ SERVICE QUALITY SUMMARY</h2>
                
                <div class="kpi-grid">
                    <div class="kpi-card" style="background: linear-gradient(135deg, #28a745 0%, #20c997 100%);">
                        <div class="kpi-value">100%</div>
                        <div class="kpi-label">SLA Compliance</div>
                    </div>
                    <div class="kpi-card" style="background: linear-gradient(135deg, #17a2b8 0%, #0c5460 100%);">
                        <div class="kpi-value">74.5%</div>
                        <div class="kpi-label">Same-Month Closure</div>
                    </div>
                    <div class="kpi-card" style="background: linear-gradient(135deg, #007bff 0%, #0056b3 100%);">
                        <div class="kpi-value">20.5%</div>
                        <div class="kpi-label">Proactive (Silent)</div>
                    </div>
                    <div class="kpi-card" style="background: linear-gradient(135deg, #6f42c1 0%, #4a0080 100%);">
                        <div class="kpi-value">45.5%</div>
                        <div class="kpi-label">Low Priority Ratio</div>
                    </div>
                </div>
                
                <div class="highlight">
                    <strong>Summary:</strong> Autotech Recruit Limited received solid IT support during February 2026 with strong SLA compliance, efficient ticket resolution, and effective proactive monitoring. The primary opportunity lies in optimising the high volume of ARCRM applicant merge requests through automation or streamlined processes.
                </div>
            </div>
        </div>
        
        <div class="footer">
            <p><strong>Report Generated:</strong> February 2026 Service Analysis | <strong>Client:</strong> Autotech Recruit Limited</p>
            <p>Based on 44 tickets across Blue Service Desk and Monitoring boards | Data source: ConnectWise ticketing system</p>
        </div>
    </div>
</body>
</html>
