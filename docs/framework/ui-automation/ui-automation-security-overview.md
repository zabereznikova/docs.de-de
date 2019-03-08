---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: 926fed8b2f03e90fd3ccf85564a20ff7b2a7d687
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674379"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="d54d1-102">Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d54d1-102">UI Automation Security Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="d54d1-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d54d1-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d54d1-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d54d1-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d54d1-105">In dieser Übersicht wird das Sicherheitsmodell für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d54d1-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span></span>  
  
<a name="User_Account_Control"></a>   
## <a name="user-account-control"></a><span data-ttu-id="d54d1-106">Benutzerkontensteuerung</span><span class="sxs-lookup"><span data-stu-id="d54d1-106">User Account Control</span></span>  
 <span data-ttu-id="d54d1-107">Sicherheit stellt einen zentralen Schwerpunkt von [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] dar, und zu den Neuerungen zählt die Möglichkeit für Benutzer, mit einer Anmeldung als Standardbenutzer (ohne Administratorberechtigungen) zu arbeiten, ohne grundsätzlich von der Ausführung von Anwendungen und Diensten ausgeschlossen zu sein, für die erhöhte Rechte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d54d1-107">Security is a major focus of [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>  
  
 <span data-ttu-id="d54d1-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]werden die meisten Anwendungen entweder mit einem Standard- oder einem Administratortoken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d54d1-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="d54d1-109">Wenn eine Anwendung nicht als Administratoranwendung identifiziert werden kann, wird sie standardmäßig als Standardanwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="d54d1-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="d54d1-110">Vor dem Starten einer Anwendung, die als Administratoranwendung identifiziert wurde, bittet [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] den Benutzer um seine Zustimmung zur Ausführung der Anwendung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="d54d1-110">Before an application identified as administrative can be launched, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="d54d1-111">Die Aufforderung zur Zustimmung wird standardmäßig angezeigt, auch wenn der Benutzer ein Mitglied der lokalen Administratorgruppe ist, da auch Administratoren mit den Rechten von Standardbenutzern agieren, bis eine Anwendung oder Systemkomponente, für die Administratorberechtigungen erforderlich sind, die Ausführungserlaubnis anfordert.</span><span class="sxs-lookup"><span data-stu-id="d54d1-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>  
  
<a name="Tasks_Requiring_Higher_Privileges"></a>   
## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="d54d1-112">Aufgaben, für die erhöhte Rechte erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="d54d1-112">Tasks Requiring Higher Privileges</span></span>  
 <span data-ttu-id="d54d1-113">Wenn ein Benutzer versucht, eine Aufgabe auszuführen, für die Administratorberechtigungen erforderlich sind, zeigt [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] ein Dialogfeld an, das den Benutzer um seine Zustimmung zur weiteren Ausführung bittet.</span><span class="sxs-lookup"><span data-stu-id="d54d1-113">When a user attempts to perform a task that requires administrative privileges, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="d54d1-114">Dieses Dialogfeld ist gegen prozessübergreifenden Datenaustausch geschützt, sodass Schadsoftware keine Benutzereingaben simulieren kann.</span><span class="sxs-lookup"><span data-stu-id="d54d1-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="d54d1-115">Analog dazu kann auch auf den Anmeldebildschirm auf dem Desktop nicht durch andere Prozesse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d54d1-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>  
  
 <span data-ttu-id="d54d1-116">Benutzeroberflächenautomatisierungs-Clients müssen mit anderen Prozessen kommunizieren, von denen einige möglicherweise mit erhöhten Rechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d54d1-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="d54d1-117">Darüber hinaus benötigen Clients möglicherweise Zugriff auf die Systemdialogfelder, die für andere Prozesse normalerweise nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="d54d1-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="d54d1-118">Daher müssen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Clients aus Sicht des Systems als vertrauenswürdig eingestuft sein und mit besonderen Berechtigungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d54d1-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>  
  
 <span data-ttu-id="d54d1-119">Damit sie für den Datenaustausch mit Anwendungen, die mit höheren Berechtigungsstufen ausgeführt werden, als vertrauenswürdig angesehen werden, müssen Anwendungen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="d54d1-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>  
  
<a name="Manifest_Files"></a>   
## <a name="manifest-files"></a><span data-ttu-id="d54d1-120">Manifestdateien</span><span class="sxs-lookup"><span data-stu-id="d54d1-120">Manifest Files</span></span>  
 <span data-ttu-id="d54d1-121">Um Zugriff auf die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]des geschützten Systems zu erhalten, müssen Anwendungen mit einer Manifestdatei generiert werden, die ein besonderes Attribut in der Manifestdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="d54d1-121">To gain access to the protected system [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], applications must be built with a manifest file that includes a special attribute in the manifest file.</span></span> <span data-ttu-id="d54d1-122">Dieses `uiAccess` -Attribut ist im `requestedExecutionLevel` -Tag enthalten, wie hier dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d54d1-122">This `uiAccess` attribute is included in the `requestedExecutionLevel` tag, as follows:</span></span>  
  
 `<trustInfo xmlns="urn:0073chemas-microsoft-com:asm.v3">`  
  
 `<security>`  
  
 `<requestedPrivileges>`  
  
 `<requestedExecutionLevel`  
  
 `level="highestAvailable"`  
  
 `UIAccess="true" />`  
  
 `</requestedPrivileges>`  
  
 `</security>`  
  
 `</trustInfo>`  
  
 <span data-ttu-id="d54d1-123">Der Wert des `level` -Attributs in diesem Code stellt nur ein Beispiel dar.</span><span class="sxs-lookup"><span data-stu-id="d54d1-123">The value of the `level` attribute in this code is an example only.</span></span>  
  
 <span data-ttu-id="d54d1-124">`UIAccess` ist standardmäßig „false“; d.h., wenn das Attribut ausgelassen wird oder kein Manifest für die Assembly vorhanden ist, kann die Anwendung keinen Zugriff auf die geschützte [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]erhalten.</span><span class="sxs-lookup"><span data-stu-id="d54d1-124">`UIAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="d54d1-125">Weitere Informationen zu [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] Sicherheit, zum Signieren von Anwendungen und zum Erstellen von Assemblymanifesten finden Sie unter [Developer Best Practices and Guidelines for Applications in a Least Privileged Environment](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="d54d1-125">For more information on [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] security, on signing applications, and on creating assembly manifests, see [Developer Best Practices and Guidelines for Applications in a Least Privileged Environment](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10)).</span></span>
