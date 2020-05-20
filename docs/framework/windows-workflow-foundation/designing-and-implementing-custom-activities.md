---
title: Entwerfen und Implementieren von benutzerdefinierten Aktivitäten
description: Dieser Artikel enthält Ressourcen zum Erstellen benutzerdefinierter Aktivitäten in Workflow Foundation, indem Sie zusammengesetzte Aktivitäten erstellen oder neue Aktivitätstypen erstellen.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 9c184bff9518bb5581f3bf4cd408db224736192b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419992"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="ed49f-103">Entwerfen und Implementieren von benutzerdefinierten Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="ed49f-103">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="ed49f-104">Benutzerdefinierte Aktivitäten in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] werden erstellt, indem entweder vom System bereitgestellte Aktivitäten zu zusammengesetzten Aktivitäten zusammengefasst oder indem neue Typen erstellt werden, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> oder <xref:System.Activities.NativeActivity> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ed49f-104">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="ed49f-105">In diesem Abschnitt wird beschrieben, wie benutzerdefinierte Aktivitäten mit diesen beiden Methoden erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ed49f-105">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ed49f-106">Benutzerdefinierte Aktivitäten werden im Workflow-Designer standardmäßig als einfaches Rechteck mit dem Namen der Aktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed49f-106">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="ed49f-107">Um eine benutzerdefinierte grafische Darstellung der Aktivität im Workflow-Designer bereitzustellen, müssen Sie auch einen benutzerdefinierten Designer erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed49f-107">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="ed49f-108">Weitere Informationen finden Sie unter [Verwenden von benutzerdefinierten Aktivitäts Designern und Vorlagen](using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="ed49f-108">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed49f-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ed49f-109">In This Section</span></span>  
 [<span data-ttu-id="ed49f-110">Aktivitätserstellungsoptionen</span><span class="sxs-lookup"><span data-stu-id="ed49f-110">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="ed49f-111">Erläutert die in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] verfügbaren Erstellungsformate.</span><span class="sxs-lookup"><span data-stu-id="ed49f-111">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="ed49f-112">Verwenden einer benutzerdefinierten Aktivität</span><span class="sxs-lookup"><span data-stu-id="ed49f-112">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="ed49f-113">Beschreibt, wie einem Workflowprojekt eine benutzerdefinierte Aktivität hinzufügt wird.</span><span class="sxs-lookup"><span data-stu-id="ed49f-113">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="ed49f-114">Erstellen von asynchronen Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="ed49f-114">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="ed49f-115">Beschreibt die Erstellung asynchroner Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="ed49f-115">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="ed49f-116">Konfigurieren der Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="ed49f-116">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="ed49f-117">Beschreibt, wie die Aktivitätsvalidierung verwendet werden kann, um Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden.</span><span class="sxs-lookup"><span data-stu-id="ed49f-117">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="ed49f-118">Erstellen einer Aktivität zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ed49f-118">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="ed49f-119">Erläutert, wie Aktivitäten zur Laufzeit mithilfe von <xref:System.Activities.DynamicActivity> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ed49f-119">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="ed49f-120">Eigenschaften der Workflowausführung</span><span class="sxs-lookup"><span data-stu-id="ed49f-120">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="ed49f-121">Beschreibt, wie die Eigenschaften der Workflowausführung verwendet werden, um der Umgebung einer Aktivität kontextspezifische Eigenschaften hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ed49f-121">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="ed49f-122">Verwenden von Aktivitätsdelegaten</span><span class="sxs-lookup"><span data-stu-id="ed49f-122">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="ed49f-123">Erläutert, wie Aktivitäten erstellt und verwendet werden, die Aktivitätsdelegaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed49f-123">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="ed49f-124">Verwenden von Aktivitätserweiterungen</span><span class="sxs-lookup"><span data-stu-id="ed49f-124">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="ed49f-125">Beschreibt, wie Aktivitätserweiterungen erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed49f-125">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="ed49f-126">Verarbeiten von OData-Feeds eines Workflows</span><span class="sxs-lookup"><span data-stu-id="ed49f-126">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="ed49f-127">Beschreibt verschiedene Möglichkeiten zum Aufrufen eines WCF Data Service aus einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="ed49f-127">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="ed49f-128">Bereichsauswahl und Sichtbarkeit der Aktivitätsdefinition</span><span class="sxs-lookup"><span data-stu-id="ed49f-128">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="ed49f-129">Beschreibt die Optionen und Regeln zum Definieren von Datenbereichen sowie der Membersichtbarkeit für Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="ed49f-129">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
