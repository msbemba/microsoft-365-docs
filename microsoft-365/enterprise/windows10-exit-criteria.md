---
title: "Phase 3: Windows 10 Enterprise infrastructure exit criteria"
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection: 
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom:
description: Ensure that your configuration meets Microsoft 365 Enterprise criteria for Windows 10 Enterprise.
---

# Phase 3: Windows 10 Enterprise infrastructure exit criteria

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.

<a name="crit-windows10-step1"></a>
## Required: Your Microsoft 365 domains are added and verified

The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”. 

If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.

If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.

## Optional: Your users are added and licensed

The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).

Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.

If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.

## Optional: Diagnostics are enabled

You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.

If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.

<a name="crit-windows10-step2"></a>
## Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment

To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:

- Set the proper Windows diagnostics data level
- Verified the readiness to upgrade Windows
- Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image

Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can. 

Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.

If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.

<a name="crit-windows10-step3"></a>
## Required for new devices: Configured Windows Autopilot

To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:

- Configured the proper Windows diagnostics data level
- Configured the prerequisites for Windows Autopilot, which include:
   - Device registration and OOBE customization
   - Company branding for OOBE
   - MDM auto-enrollment in Microsoft Intune
   - Network connectivity to cloud services used by Windows Autopilot
- Devices that are pre-installed with Windows 10, version 1703 or later
- Selected the Windows Autopilot Deployment Program for your organization

Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:

- New devices
- Devices that have already completed an out-of-box setup in your organization. 

Windows Autopilot configures the device and connects it to Azure AD.

Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.

If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.

<a name="crit-windows10-step4"></a>
## Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices

You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization. 

If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.

<a name="crit-windows10-step5a"></a>
## Required: You are using Windows Defender Antivirus or your own antimalware solution

You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.

If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.

<a name="crit-windows10-step5b"></a>
## Required: You are using Windows Defender Exploit Guard

You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.

If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.

<a name="crit-windows10-step5c"></a>
## Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)

You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise. 

Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.

If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.

## Results and next steps

Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md). |
