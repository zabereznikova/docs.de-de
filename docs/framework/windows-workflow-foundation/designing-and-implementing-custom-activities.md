---
title: Entwerfen und Implementieren von benutzerdefinierten Aktivitäten
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 673145c856e950c8648a87cb3dcb9665ffa51ba9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216713"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="e9a5b-102">Entwerfen und Implementieren von benutzerdefinierten Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="e9a5b-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="e9a5b-103">Benutzerdefinierte Aktivitäten in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] werden erstellt, indem entweder vom System bereitgestellte Aktivitäten zu zusammengesetzten Aktivitäten zusammengefasst oder indem neue Typen erstellt werden, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> oder <xref:System.Activities.NativeActivity> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="e9a5b-104">In diesem Abschnitt wird beschrieben, wie benutzerdefinierte Aktivitäten mit diesen beiden Methoden erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9a5b-105">Benutzerdefinierte Aktivitäten werden im Workflow-Designer standardmäßig als einfaches Rechteck mit dem Namen der Aktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="e9a5b-106">Um eine benutzerdefinierte grafische Darstellung der Aktivität im Workflow-Designer bereitzustellen, müssen Sie auch einen benutzerdefinierten Designer erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="e9a5b-107">Weitere Informationen finden Sie unter [mithilfe von benutzerdefinierten Aktivitätsdesigner und Vorlagen](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e9a5b-107">For more information, see [Using Custom Activity Designers and Templates](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9a5b-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9a5b-108">In This Section</span></span>  
 [<span data-ttu-id="e9a5b-109">Aktivitätserstellungsoptionen</span><span class="sxs-lookup"><span data-stu-id="e9a5b-109">Activity Authoring Options</span></span>](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 <span data-ttu-id="e9a5b-110">Erläutert die in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] verfügbaren Erstellungsformate.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="e9a5b-111">Verwenden einer benutzerdefinierten Aktivität</span><span class="sxs-lookup"><span data-stu-id="e9a5b-111">Using a custom activity</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 <span data-ttu-id="e9a5b-112">Beschreibt, wie einem Workflowprojekt eine benutzerdefinierte Aktivität hinzufügt wird.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="e9a5b-113">Erstellen von asynchronen Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="e9a5b-113">Creating Asynchronous Activities</span></span>](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="e9a5b-114">Beschreibt die Erstellung asynchroner Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="e9a5b-115">Konfigurieren der Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="e9a5b-115">Configuring Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 <span data-ttu-id="e9a5b-116">Beschreibt, wie die Aktivitätsvalidierung verwendet werden kann, um Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="e9a5b-117">Erstellen einer Aktivität zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e9a5b-117">Creating an Activity at Runtime</span></span>](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="e9a5b-118">Erläutert, wie Aktivitäten zur Laufzeit mithilfe von <xref:System.Activities.DynamicActivity> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="e9a5b-119">Eigenschaften der Workflowausführung</span><span class="sxs-lookup"><span data-stu-id="e9a5b-119">Workflow Execution Properties</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 <span data-ttu-id="e9a5b-120">Beschreibt, wie die Eigenschaften der Workflowausführung verwendet werden, um der Umgebung einer Aktivität kontextspezifische Eigenschaften hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="e9a5b-121">Verwenden von Aktivitätsdelegaten</span><span class="sxs-lookup"><span data-stu-id="e9a5b-121">Using Activity Delegates</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 <span data-ttu-id="e9a5b-122">Erläutert, wie Aktivitäten erstellt und verwendet werden, die Aktivitätsdelegaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-122">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="e9a5b-123">Verwenden von Aktivitätserweiterungen</span><span class="sxs-lookup"><span data-stu-id="e9a5b-123">Using Activity Extensions</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 <span data-ttu-id="e9a5b-124">Beschreibt, wie Aktivitätserweiterungen erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-124">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="e9a5b-125">Verarbeiten von OData-Feeds eines Workflows</span><span class="sxs-lookup"><span data-stu-id="e9a5b-125">Consuming OData Feeds from a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="e9a5b-126">Beschreibt verschiedene Möglichkeiten zum Aufrufen eines WCF Data Service aus einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-126">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="e9a5b-127">Bereichsauswahl und Sichtbarkeit der Aktivitätsdefinition</span><span class="sxs-lookup"><span data-stu-id="e9a5b-127">Activity Definition Scoping and Visibility</span></span>](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="e9a5b-128">Beschreibt die Optionen und Regeln zum Definieren von Datenbereichen sowie der Membersichtbarkeit für Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="e9a5b-128">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
