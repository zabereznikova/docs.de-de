---
title: Konfigurieren der Aktivitätsvalidierung
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: c3e10fc096b16ef2cf7a6c7533ac9bad8c5ec205
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288956"
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="4a0ce-102">Konfigurieren der Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="4a0ce-102">Configuring Activity Validation</span></span>

<span data-ttu-id="4a0ce-103">Die Aktivitätsvalidierung ermöglicht es Autoren und Benutzern von Aktivitäten, Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> <span data-ttu-id="4a0ce-104">Windows Workflow Foundation (WF) stellt die folgenden drei Arten der Aktivitäts Validierung bereit:</span><span class="sxs-lookup"><span data-stu-id="4a0ce-104">Windows Workflow Foundation (WF) provides the following three types of activity validation:</span></span>  
  
- <span data-ttu-id="4a0ce-105">`RequiredArgument`-Attribute und `OverloadGroup`-Attribute</span><span class="sxs-lookup"><span data-stu-id="4a0ce-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
- <span data-ttu-id="4a0ce-106">Imperative codebasierte Validierung</span><span class="sxs-lookup"><span data-stu-id="4a0ce-106">Imperative code-based validation.</span></span>  
  
- <span data-ttu-id="4a0ce-107">Deklarative Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4a0ce-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="4a0ce-108">Das `RequiredArgument`-Attribut und das `OverloadGroup`-Attribut geben an, dass bestimmte Argumente für eine Aktivität erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="4a0ce-109">Die imperative codebasierte Validierung stellt eine problemlose Möglichkeit für eine Aktivität dar, sich selbst zu validieren. Deklarative Einschränkungen ermöglichen die Validierung der Aktivität und ihrer Beziehung zum enthaltenden Workflow.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="4a0ce-110">Wenn eine Aktivität nicht ordnungsgemäß nach den Validierungsanforderungen konfiguriert wird, werden Validierungsfehler und -warnungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="4a0ce-111">Wenn der enthaltende Workflow mit dem Workflow-Designer erstellt wird, werden alle Validierungsfehler und -warnungen im Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="4a0ce-112">Falls der Workflow außerhalb des Workflow-Designers erstellt wird, werden alle Validierungsfehler beim Aufrufen des Workflows zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="4a0ce-113">Unabhängig von der Art der Erstellung des Workflows ist die Ausführung eines Workflows mit Validierungsfehlern nie zulässig.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="4a0ce-114">Dieser Abschnitt bietet eine Übersicht über diese Arten der Aktivitätsvalidierung und den Aufruf der Aktivitätsvalidierung.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a0ce-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4a0ce-115">In This Section</span></span>  

 [<span data-ttu-id="4a0ce-116">Erforderliche Argumente und Überladungsgruppen</span><span class="sxs-lookup"><span data-stu-id="4a0ce-116">Required Arguments and Overload Groups</span></span>](required-arguments-and-overload-groups.md)  
 <span data-ttu-id="4a0ce-117">Beschreibt die Verwendung des `RequiredArgument`-Attributs und des `OverloadGroup`-Attributs zur Bereitstellung der Validierung.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="4a0ce-118">Imperative codebasierte Validierung</span><span class="sxs-lookup"><span data-stu-id="4a0ce-118">Imperative Code-Based Validation</span></span>](imperative-code-based-validation.md)  
 <span data-ttu-id="4a0ce-119">Beschreibt die Verwendung der codebasierten Validierung für Aktivitäten auf Grundlage von <xref:System.Activities.CodeActivity> und <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="4a0ce-120">Deklarative Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4a0ce-120">Declarative Constraints</span></span>](declarative-constraints.md)  
 <span data-ttu-id="4a0ce-121">Beschreibt die Verwendung von deklarativen Einschränkungen für die Bereitstellung einer komplexen Aktivitätsvalidierung.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="4a0ce-122">Aufrufen der Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="4a0ce-122">Invoking Activity Validation</span></span>](invoking-activity-validation.md)  
 <span data-ttu-id="4a0ce-123">Erläutert, wann die Aktivitätsvalidierung automatisch aufgerufen wird und wie die Validierung explizit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4a0ce-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4a0ce-124">Referenz</span><span class="sxs-lookup"><span data-stu-id="4a0ce-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4a0ce-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4a0ce-125">Related Sections</span></span>
