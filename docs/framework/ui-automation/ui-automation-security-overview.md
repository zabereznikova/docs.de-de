---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit
description: Lesen Sie eine Übersicht über das Sicherheitsmodell für Microsoft UI Automation. Verstehen Sie die Benutzerkontensteuerung, Aufgaben, die höhere Berechtigungen erfordern, und Manifestressourcen.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: d483f282db8ce8e5653d6d83361fa44df05f63f5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163138"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="1172f-104">Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1172f-104">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="1172f-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1172f-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1172f-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="1172f-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="1172f-107">In dieser Übersicht wird das Sicherheitsmodell für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1172f-107">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="1172f-108">Benutzerkontensteuerung</span><span class="sxs-lookup"><span data-stu-id="1172f-108">User Account Control</span></span>

<span data-ttu-id="1172f-109">Sicherheit ist ein wichtiger Schwerpunkt von Windows Vista. zu den Neuerungen zählt die Möglichkeit für Benutzer, als Standardbenutzer (nicht Administrator) auszuführen, ohne dass die Ausführung von Anwendungen und Diensten, die höhere Berechtigungen erfordern, nicht unbedingt blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="1172f-109">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="1172f-110">In Windows Vista werden die meisten Anwendungen entweder mit einem Standard-oder einem Administrator Token bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1172f-110">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="1172f-111">Wenn eine Anwendung nicht als Administratoranwendung identifiziert werden kann, wird sie standardmäßig als Standardanwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="1172f-111">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="1172f-112">Bevor eine Anwendung, die als administrative Anwendung identifiziert wird, gestartet werden kann, fordert Windows Vista den Benutzer zur Zustimmung auf, die Anwendung mit erhöhten Rechten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1172f-112">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="1172f-113">Die Aufforderung zur Zustimmung wird standardmäßig angezeigt, auch wenn der Benutzer ein Mitglied der lokalen Administratorgruppe ist, da auch Administratoren mit den Rechten von Standardbenutzern agieren, bis eine Anwendung oder Systemkomponente, für die Administratorberechtigungen erforderlich sind, die Ausführungserlaubnis anfordert.</span><span class="sxs-lookup"><span data-stu-id="1172f-113">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="1172f-114">Aufgaben, für die erhöhte Rechte erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="1172f-114">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="1172f-115">Wenn ein Benutzer versucht, eine Aufgabe auszuführen, für die Administrator Berechtigungen erforderlich sind, zeigt Windows Vista ein Dialogfeld an, in dem der Benutzer zum Fortfahren aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="1172f-115">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="1172f-116">Dieses Dialogfeld ist gegen prozessübergreifenden Datenaustausch geschützt, sodass Schadsoftware keine Benutzereingaben simulieren kann.</span><span class="sxs-lookup"><span data-stu-id="1172f-116">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="1172f-117">Analog dazu kann auch auf den Anmeldebildschirm auf dem Desktop nicht durch andere Prozesse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1172f-117">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="1172f-118">Benutzeroberflächenautomatisierungs-Clients müssen mit anderen Prozessen kommunizieren, von denen einige möglicherweise mit erhöhten Rechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1172f-118">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="1172f-119">Darüber hinaus benötigen Clients möglicherweise Zugriff auf die Systemdialogfelder, die für andere Prozesse normalerweise nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="1172f-119">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="1172f-120">Daher müssen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Clients aus Sicht des Systems als vertrauenswürdig eingestuft sein und mit besonderen Berechtigungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1172f-120">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="1172f-121">Damit sie für den Datenaustausch mit Anwendungen, die mit höheren Berechtigungsstufen ausgeführt werden, als vertrauenswürdig angesehen werden, müssen Anwendungen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="1172f-121">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="1172f-122">Manifestdateien</span><span class="sxs-lookup"><span data-stu-id="1172f-122">Manifest Files</span></span>

<span data-ttu-id="1172f-123">Für den Zugriff auf die Benutzeroberfläche des geschützten Systems müssen Anwendungen wie folgt mit einer Manifest-Datei erstellt werden, die das- `uiAccess` Attribut im- `requestedExecutionLevel` Tag enthält:</span><span class="sxs-lookup"><span data-stu-id="1172f-123">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="1172f-124">Der Wert des `level` -Attributs in diesem Code stellt nur ein Beispiel dar.</span><span class="sxs-lookup"><span data-stu-id="1172f-124">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="1172f-125">`uiAccess`ist standardmäßig "false"; Das heißt, wenn das Attribut ausgelassen wird oder kein Manifest für die Assembly vorhanden ist, kann die Anwendung keinen Zugriff auf die geschützte Benutzeroberfläche erhalten.</span><span class="sxs-lookup"><span data-stu-id="1172f-125">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>
