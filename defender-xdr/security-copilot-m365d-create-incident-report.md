---
title: Create incident reports with Microsoft Copilot in Microsoft Defender
description: Write incident reports with Microsoft Copilot in Microsoft Defender.
keywords: security copilot, Microsoft Defender XDR, embedded experience, incident report, script analyzer, script analysis, query assistant, m365, incident report, guided response, incident response playbooks, incident response, incident report creation, create report, create incident report, write incident report, write report, Microsoft Copilot for Security, Microsoft Defender, Copilot in Defender
ms.service: defender-xdr
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
  - NOCSH
ms.author: diannegali
author: diannegali
ms.localizationpriority: medium
manager: deniseb
audience: ITPro
ms.collection:
  - m365-security
  - tier1
ms.topic: conceptual
search.appverid:
  - MOE150
  - MET150
ms.date: 03/28/2024
---

# Create an incident report with Microsoft Copilot in Microsoft Defender

[!INCLUDE [Microsoft Defender XDR rebranding](../includes/microsoft-defender.md)]

**Applies to:**

- Microsoft Defender XDR
- Microsoft Defender unified security operations center (SOC) platform

[Microsoft Copilot for Security](/security-copilot/microsoft-security-copilot) in the Microsoft Defender portal assists security operations teams with writing incident reports efficiently. Utilizing Copilot for Security's AI-powered data processing, security teams can immediately create incident reports with a click of a button in the Microsoft Defender portal.

A comprehensive and clear incident report is an essential reference for security teams and security operations management. However, writing a comprehensive report with the important details present can be a time-consuming task for security operations teams. Collecting, organizing, and summarizing incident information from multiple sources requires focus and detailed analysis to create an information-rich report. With Copilot in Defender, security teams can now instantly create an extensive incident report within the portal.

While an [incident summary](security-copilot-m365d-incident-summary.md) provides an overview of an incident and how it happened, an incident report consolidates incident information from various data sources available in Microsoft Sentinel and Defender XDR. The Copilot-generated incident report also includes all analyst-driven steps and automated actions, the analysts involved in incident response, and the comments from the analysts. Whether security teams are using Microsoft Sentinel, Defender XDR, or both, all relevant incident data are added into the generated incident report. 

Copilot generates the incident report based on the automatic and manual actions implemented, and the analysts' comments and notes posted in the incident. You can review and follow [recommendations](security-copilot-m365d-create-incident-report.md#recommendations-for-incident-report-creation) to ensure that Copilot creates a comprehensive incident report.

The incident report generation capability in Microsoft Defender is available through the [Copilot for Security license](/security-copilot/faq-security-copilot). This capability is also available in the Copilot for Security standalone portal through the Microsoft Defender XDR plugin.

This guide lists the data in incident reports and contains steps on how to access the incident report creation capability within the Microsoft Defender portal. It also includes information on how to provide feedback about the generated report.

## Incident report content

Copilot in Defender creates an incident report containing the following information:

- The main incident management actions' timestamps, including:
  - Incident creation and closure
  - First and last logs, whether the log was analyst-driven or automated, captured in the incident
- The analysts involved in incident response
- [Incident classification](manage-incidents.md#specify-the-classification), including analysts' comments on how the incident was evaluated and classified.
- Investigation and remediation actions
- Follow up actions like recommendations, open issues, or next steps noted by the analysts in the incident logs

In particular, the incident report includes data from the following automatic and manually triggered actions:

|Action source|Description|
|---|---|
|[Live response API](/microsoft-365/security/defender-endpoint/api/run-live-response)|Live response commands that ran through the live response API|
|[Live response commands](/microsoft-365/security/defender-endpoint/live-response)|Live response commands that ran on a device|
|[Response actions on a device](/microsoft-365/security/defender-endpoint/respond-machine-alerts)|Defender for Endpoint response actions that an analyst ran on a device|
|[Response actions on a file](/microsoft-365/security/defender-endpoint/respond-file-alerts)|Defender for Endpoint response actions that an analyst ran on a file|
|[Manual remediation actions applied to user accounts and email](m365d-remediation-actions.md#remediation-actions-that-are-taken-manually)|Manual remediation actions taken by analysts on user accounts and email after automated investigations in Defender XDR|
|[Manual remediation actions taken from query results of advanced hunting](advanced-hunting-take-action.md)|Manual remediation actions taken by analysts on devices and files out of the results from advanced hunting queries|
|[Microsoft Sentinel playbooks ran](/azure/sentinel/automate-responses-with-playbooks)|Microsoft Sentinel playbooks used in investigation and response|

   > [!NOTE]
   > Response actions coming from public API sources or from custom detections are not yet supported.

## Create an incident report

To create an incident report with Copilot in Defender, perform the following steps:

1. Open an incident page. In the incident page, navigate to the **More actions** ellipsis (...) and then select **Generate incident report**. Alternately, you can select the report icon found in the Copilot side panel.

   :::image type="content" source="./media/copilot-in-defender/incident-report/copilot-defender-incident-report-small.png" alt-text="Screenshot highlighting the generated incident report and report icon buttons in the incident page." lightbox="./media/copilot-in-defender/incident-report/copilot-defender-incident-report.png":::

2. Copilot creates the incident report. You can stop the report creation by selecting **Cancel** and restart report creation by selecting **Regenerate**. Additionally, you can restart report creation if you encounter an error.

3. The incident report card appears on the Copilot pane. The generated report depends on the incident information available from Microsoft Defender XDR and Microsoft Sentinel. Refer to the [recommendations](security-copilot-m365d-create-incident-report.md#recommendations-for-incident-report-creation) to ensure a comprehensive incident report.

   :::image type="content" source="./media/copilot-in-defender/incident-report/copilot-defender-incident-report-results1-small.png" alt-text="Screenshot of the incident report card in the incident page." lightbox="./media/copilot-in-defender/incident-report/copilot-defender-incident-report-results1.png":::

   :::image type="content" source="./media/copilot-in-defender/incident-report/copilot-defender-incident-report-results2-small.png" alt-text="Screenshot of the incident report card in the incident page showing the lower bottom of the card." lightbox="./media/copilot-in-defender/incident-report/copilot-defender-incident-report-results2.png":::

4. Select the More actions ellipsis (...) located on the upper right of the incident report card. To copy the report, select **Copy to clipboard** and paste the report to your preferred system, or **Post to activity log** to add the report to the comments and history of the incident. Select **Regenerate** to restart report creation. You can also **Open in Copilot for Security** to view the results and continue accessing other plugins available in the Copilot for Security standalone portal.

   ![Screenshot of additional actions in the incident report results card.](./media/copilot-in-defender/incident-report/copilot-defender-incident-report-more-actions.png)

5. Review the generated incident report. You can provide feedback on the report by selecting the feedback icon found on the bottom of the results  ![Screenshot of the feedback icon for Copilot in Defender cards](./media/copilot-in-defender/copilot-defender-feedback.png).

## Recommendations for incident report creation

Here are some recommendations to consider to ensure that Copilot generates a comprehensive and complete incident report:

- Classify and resolve the incident before generating the incident report.
- Ensure that you write and save comments in the Microsoft Sentinel activity log or in the Microsoft Defender XDR incident comments and history to include the comments in the incident report.
- Write comments using comprehensive and clear language. In-depth and clear comments provide better context about the response actions. See the following steps to know how to access the comments field:
  - [Add comments to incidents in Microsoft Defender XDR](manage-incidents.md#add-comments)
  - [Add comments to incidents in Microsoft Sentinel](/azure/sentinel/investigate-cases#comment-on-incidents)
- For ServiceNow users, [enable the Microsoft Sentinel and ServiceNow bi-directional sync](https://techcommunity.microsoft.com/t5/microsoft-sentinel-blog/what-s-new-introducing-microsoft-sentinel-solution-for/ba-p/3692840) to get more robust incident data.
- Copy the generated incident report and post it to the comments and history of the incident to ensure that the incident report is saved in the incident page.

## See also

- [Get started with Microsoft Copilot for Security](/security-copilot/get-started-security-copilot)
- [Learn about other Copilot for Security embedded experiences](/security-copilot/experiences-security-copilot)
- Know more about [preinstalled plugins in Copilot for Security](/security-copilot/manage-plugins#preinstalled-plugins)

[!INCLUDE [Microsoft Defender XDR rebranding](../includes/defender-m3d-techcommunity.md)]