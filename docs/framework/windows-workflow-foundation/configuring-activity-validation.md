---
title: Konfigurieren der Aktivitätsvalidierung
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: 6c971b56e269fbb330bd9ad0a551a9fb9ca01196
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655111"
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="a1082-102">Konfigurieren der Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="a1082-102">Configuring Activity Validation</span></span>
<span data-ttu-id="a1082-103">Die Aktivitätsvalidierung ermöglicht es Autoren und Benutzern von Aktivitäten, Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden.</span><span class="sxs-lookup"><span data-stu-id="a1082-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> <span data-ttu-id="a1082-104">Windows Workflow Foundation (WF) stellt die folgenden drei Arten von aktivitätsvalidierung bereit:</span><span class="sxs-lookup"><span data-stu-id="a1082-104">Windows Workflow Foundation (WF) provides the following three types of activity validation:</span></span>  
  
- <span data-ttu-id="a1082-105">`RequiredArgument`-Attribute und `OverloadGroup`-Attribute</span><span class="sxs-lookup"><span data-stu-id="a1082-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
- <span data-ttu-id="a1082-106">Imperative codebasierte Validierung</span><span class="sxs-lookup"><span data-stu-id="a1082-106">Imperative code-based validation.</span></span>  
  
- <span data-ttu-id="a1082-107">Deklarative Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a1082-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="a1082-108">Das `RequiredArgument`-Attribut und das `OverloadGroup`-Attribut geben an, dass bestimmte Argumente für eine Aktivität erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a1082-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="a1082-109">Die imperative codebasierte Validierung stellt eine problemlose Möglichkeit für eine Aktivität dar, sich selbst zu validieren. Deklarative Einschränkungen ermöglichen die Validierung der Aktivität und ihrer Beziehung zum enthaltenden Workflow.</span><span class="sxs-lookup"><span data-stu-id="a1082-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="a1082-110">Wenn eine Aktivität nicht ordnungsgemäß nach den Validierungsanforderungen konfiguriert wird, werden Validierungsfehler und -warnungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a1082-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="a1082-111">Wenn der enthaltende Workflow mit dem Workflow-Designer erstellt wird, werden alle Validierungsfehler und -warnungen im Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1082-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="a1082-112">Falls der Workflow außerhalb des Workflow-Designers erstellt wird, werden alle Validierungsfehler beim Aufrufen des Workflows zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a1082-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="a1082-113">Unabhängig von der Art der Erstellung des Workflows ist die Ausführung eines Workflows mit Validierungsfehlern nie zulässig.</span><span class="sxs-lookup"><span data-stu-id="a1082-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="a1082-114">Dieser Abschnitt bietet eine Übersicht über diese Arten der Aktivitätsvalidierung und den Aufruf der Aktivitätsvalidierung.</span><span class="sxs-lookup"><span data-stu-id="a1082-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1082-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a1082-115">In This Section</span></span>  
 [<span data-ttu-id="a1082-116">Erforderliche Argumente und Überladungsgruppen</span><span class="sxs-lookup"><span data-stu-id="a1082-116">Required Arguments and Overload Groups</span></span>](required-arguments-and-overload-groups.md)  
 <span data-ttu-id="a1082-117">Beschreibt die Verwendung des `RequiredArgument`-Attributs und des `OverloadGroup`-Attributs zur Bereitstellung der Validierung.</span><span class="sxs-lookup"><span data-stu-id="a1082-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="a1082-118">Imperative codebasierte Validierung</span><span class="sxs-lookup"><span data-stu-id="a1082-118">Imperative Code-Based Validation</span></span>](imperative-code-based-validation.md)  
 <span data-ttu-id="a1082-119">Beschreibt die Verwendung der codebasierten Validierung für Aktivitäten auf Grundlage von <xref:System.Activities.CodeActivity> und <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="a1082-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="a1082-120">Deklarative Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a1082-120">Declarative Constraints</span></span>](declarative-constraints.md)  
 <span data-ttu-id="a1082-121">Beschreibt die Verwendung von deklarativen Einschränkungen für die Bereitstellung einer komplexen Aktivitätsvalidierung.</span><span class="sxs-lookup"><span data-stu-id="a1082-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="a1082-122">Aufrufen der Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="a1082-122">Invoking Activity Validation</span></span>](invoking-activity-validation.md)  
 <span data-ttu-id="a1082-123">Erläutert, wann die Aktivitätsvalidierung automatisch aufgerufen wird und wie die Validierung explizit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a1082-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a1082-124">Referenz</span><span class="sxs-lookup"><span data-stu-id="a1082-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a1082-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a1082-125">Related Sections</span></span>
