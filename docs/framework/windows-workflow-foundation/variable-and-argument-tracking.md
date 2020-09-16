---
title: Nachverfolgung von Variablen und Argumenten
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: af5c21b75f3238546acac0755ec4e6149ee50d95
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552491"
---
# <a name="variable-and-argument-tracking"></a><span data-ttu-id="4bce2-102">Nachverfolgung von Variablen und Argumenten</span><span class="sxs-lookup"><span data-stu-id="4bce2-102">Variable and Argument Tracking</span></span>
<span data-ttu-id="4bce2-103">Bei der Nachverfolgung der Workflowausführung kann sich das Extrahieren von Daten oft als nützlich erweisen.</span><span class="sxs-lookup"><span data-stu-id="4bce2-103">When tracking the execution of a workflow, it is often useful to extract data.</span></span> <span data-ttu-id="4bce2-104">Sie stellt zusätzlichen Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="4bce2-104">This provides additional context when accessing a tracking record post execution.</span></span> <span data-ttu-id="4bce2-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] können Sie alle sichtbaren Variablen oder Argumente innerhalb des Bereichs einer Aktivität in einem Workflow mithilfe der Nachverfolgung extrahieren.</span><span class="sxs-lookup"><span data-stu-id="4bce2-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], you can extract any visible variable or argument within the scope of any activity in a workflow using tracking.</span></span> <span data-ttu-id="4bce2-106">Überwachungsprofile vereinfachen das Extrahieren von Daten.</span><span class="sxs-lookup"><span data-stu-id="4bce2-106">Tracking profiles make it easy to extract data.</span></span>  
  
## <a name="variables-and-arguments"></a><span data-ttu-id="4bce2-107">Variablen und Argumente</span><span class="sxs-lookup"><span data-stu-id="4bce2-107">Variables and Arguments</span></span>  
 <span data-ttu-id="4bce2-108">Variablen und Argumente werden extrahiert, wenn eine Aktivität einen ActivityStateRecord ausgibt.</span><span class="sxs-lookup"><span data-stu-id="4bce2-108">Variables and arguments are extracted when an activity emits an ActivityStateRecord.</span></span>  <span data-ttu-id="4bce2-109">Eine Variable kann nur extrahiert werden, wenn sie innerhalb des Bereichs der Aktivität liegt.</span><span class="sxs-lookup"><span data-stu-id="4bce2-109">A variable is available for extraction only if it is within the scope of the activity.</span></span> <span data-ttu-id="4bce2-110">Eine Variable, die in einer Aktivität extrahiert werden soll, wird wie folgt angegeben:</span><span class="sxs-lookup"><span data-stu-id="4bce2-110">A variable to be extracted within an activity is specified in the following manner:</span></span>  
  
- <span data-ttu-id="4bce2-111">Wenn eine Variable über den Variablennamen angegeben wird, sucht die Nachverfolgung in der aktuellen Aktivität, die nachverfolgt wird, und in den übergeordneten Aktivitäten nach der Variable.</span><span class="sxs-lookup"><span data-stu-id="4bce2-111">If a variable is specified by the variable name, then tracking looks for the variable within the current activity being tracked and in parent activities.</span></span> <span data-ttu-id="4bce2-112">Es wird im aktuellen Aktivitätsbereich und im übergeordneten Bereich nach der Variablen gesucht.</span><span class="sxs-lookup"><span data-stu-id="4bce2-112">The variable is searched in current activity scope and in parent scope.</span></span>  
  
- <span data-ttu-id="4bce2-113">Wenn Variablen, die extrahiert werden sollen, mit Name = " \* " angegeben werden, werden alle Variablen innerhalb der aktuellen Aktivität, die nachverfolgt werden, extrahiert.</span><span class="sxs-lookup"><span data-stu-id="4bce2-113">If variables to be extracted are specified by using name="\*", then all variables within the current activity being tracked are extracted.</span></span> <span data-ttu-id="4bce2-114">In diesem Fall werden keine Variablen extrahiert, die innerhalb des Bereichs liegen, jedoch in übergeordneten Aktivitäten definiert sind.</span><span class="sxs-lookup"><span data-stu-id="4bce2-114">In this case variables that are in scope but defined in parent activities are not extracted.</span></span>  
  
 <span data-ttu-id="4bce2-115">Beim Extrahieren von Argumenten sind die extrahierten Argumente vom Zustand der Aktivität abhängig.</span><span class="sxs-lookup"><span data-stu-id="4bce2-115">When extracting arguments, the arguments extracted depend on the state of the activity.</span></span> <span data-ttu-id="4bce2-116">Wenn der Zustand einer Aktivität Executing ist, können nur `InArguments` extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="4bce2-116">When the state of an activity is Executing, then only the `InArguments` are available for extraction.</span></span> <span data-ttu-id="4bce2-117">Bei jedem anderen Aktivitätszustand (Closed, Faulted, Canceled) können alle Argumente, InArguments und OutArguments, extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="4bce2-117">For any other activity state (Closed, Faulted, Canceled), all arguments, both InArguments and OutArguments, are available for extraction.</span></span>  
  
 <span data-ttu-id="4bce2-118">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4bce2-118">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="4bce2-119">Variablen und Argumente können nur mit einem <xref:System.Activities.Tracking.ActivityStateRecord>-Objekt extrahiert und so innerhalb eines Überwachungsprofils mit <xref:System.Activities.Tracking.ActivityStateQuery> abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="4bce2-119">Variables and arguments can be extracted only with an <xref:System.Activities.Tracking.ActivityStateRecord> and thus are subscribed to within a tracking profile using <xref:System.Activities.Tracking.ActivityStateQuery>.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a><span data-ttu-id="4bce2-120">Schützen von Informationen in Variablen und Argumenten</span><span class="sxs-lookup"><span data-stu-id="4bce2-120">Protecting Information Stored Within Variables and Arguments</span></span>  
 <span data-ttu-id="4bce2-121">Eine nachverfolgte Variable oder ein nachverfolgtes Argument wird standardmäßig von der WF-Laufzeit sichtbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="4bce2-121">A tracked variable or argument is by default made visible by the WF runtime.</span></span> <span data-ttu-id="4bce2-122">Workflowentwickler können mit folgenden Schritten einen Schutz vor Zugriffen erreichen:</span><span class="sxs-lookup"><span data-stu-id="4bce2-122">A workflow developer can protect it from being accessed by taking the following steps:</span></span>  
  
1. <span data-ttu-id="4bce2-123">Verschlüsseln Sie den Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="4bce2-123">Encrypt the value of a variable.</span></span>  
  
2. <span data-ttu-id="4bce2-124">Steuern Sie die Erstellung eines Überwachungsprofils, um das Extrahieren von Variablen oder Argumenten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4bce2-124">Control the authoring of a tracking profile to prevent the extraction of a variable or argument.</span></span>  
  
3. <span data-ttu-id="4bce2-125">Stellen Sie bei benutzerdefinierten Überwachungsteilnehmern sicher, dass im WF-Code keine vertraulichen Informationen angegeben sind, die in Variablen oder Argumenten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4bce2-125">For custom tracking participants ensure that the WF code does not disclose sensitive information that is stored in variables or arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bce2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bce2-126">See also</span></span>

- <span data-ttu-id="4bce2-127">[Windows Server-App-Fabric-Überwachung](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4bce2-127">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="4bce2-128">[Überwachen von Anwendungen mit App-Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4bce2-128">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
