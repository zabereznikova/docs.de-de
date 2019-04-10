---
title: Verwenden des ModelItem-Bearbeitungskontexts
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a2628bbbf2f6684e5d484b05cd5a2ac622f3b664
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296877"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="bafcc-102">Verwenden des ModelItem-Bearbeitungskontexts</span><span class="sxs-lookup"><span data-stu-id="bafcc-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="bafcc-103">Der <xref:System.Activities.Presentation.Model.ModelItem>-Bearbeitungskontext ist das Objekt, mit dem die Hostanwendung mit dem Designer kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="bafcc-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <xref:System.Activities.Presentation.EditingContext> <span data-ttu-id="bafcc-104">stellt zwei Methoden, <xref:System.Activities.Presentation.EditingContext.Items%2A> und <xref:System.Activities.Presentation.EditingContext.Services%2A>, die verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="bafcc-104">exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="bafcc-105">Items-Auflistung</span><span class="sxs-lookup"><span data-stu-id="bafcc-105">The Items collection</span></span>  
 <span data-ttu-id="bafcc-106">Die <xref:System.Activities.Presentation.EditingContext.Items%2A>-Auflistung wird verwendet, um auf Daten zuzugreifen, die zwischen dem Host und dem Designer freigegeben werden oder die in allen Designern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="bafcc-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="bafcc-107">Diese Auflistung verfügt über die folgenden Funktionen, auf die über die <xref:System.Activities.Presentation.ContextItemManager>-Klasse zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="bafcc-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="bafcc-108">Services-Auflistung</span><span class="sxs-lookup"><span data-stu-id="bafcc-108">The Services collection</span></span>  
 <span data-ttu-id="bafcc-109">Die <xref:System.Activities.Presentation.EditingContext.Services%2A>-Auflistung wird verwendet, um auf Dienste zuzugreifen, mit denen der Designer mit dem Host interagiert oder die von allen Designern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bafcc-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="bafcc-110">Diese Auflistung verfügt über die folgenden relevanten Methoden:</span><span class="sxs-lookup"><span data-stu-id="bafcc-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="bafcc-111">Zuweisen einer Aktivität zu einem Designer</span><span class="sxs-lookup"><span data-stu-id="bafcc-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="bafcc-112">Um anzugeben, welchen Designer eine Aktivität verwendet, wird das Designer-Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="bafcc-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="bafcc-113">Erstellen eines Diensts</span><span class="sxs-lookup"><span data-stu-id="bafcc-113">Creating a service</span></span>  
 <span data-ttu-id="bafcc-114">Zum Erstellen eines Diensts, der als Informationskanal zwischen dem Designer und dem Host agiert, müssen eine Schnittstelle und eine Implementierung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bafcc-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="bafcc-115">Die Schnittstelle wird von der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode verwendet, um die Member des Diensts zu definieren. Die Implementierung enthält die Logik für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="bafcc-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="bafcc-116">Im folgenden Codebeispiel werden eine Dienstschnittstelle und eine Implementierung erstellt.</span><span class="sxs-lookup"><span data-stu-id="bafcc-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
```  
  
## <a name="publishing-a-service"></a><span data-ttu-id="bafcc-117">Veröffentlichen eines Diensts</span><span class="sxs-lookup"><span data-stu-id="bafcc-117">Publishing a service</span></span>  
 <span data-ttu-id="bafcc-118">Damit ein Designer einen Dienst nutzt, muss dieser zuerst vom Host mit der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="bafcc-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="bafcc-119">Abonnieren eines Diensts</span><span class="sxs-lookup"><span data-stu-id="bafcc-119">Subscribing to a service</span></span>  
 <span data-ttu-id="bafcc-120">Der Designer erhält mithilfe der <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>-Methode in der <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>-Methode Zugriff auf den Dienst.</span><span class="sxs-lookup"><span data-stu-id="bafcc-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="bafcc-121">Der folgende Codeausschnitt veranschaulicht, wie ein Dienst abonniert wird.</span><span class="sxs-lookup"><span data-stu-id="bafcc-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
```  
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="bafcc-122">Freigeben von Daten mithilfe der Items-Auflistung</span><span class="sxs-lookup"><span data-stu-id="bafcc-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="bafcc-123">Das Verwenden der Items-Auflistung ähnelt der Verwendung der Services-Auflistung, außer dass <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> anstelle von "Publish" verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bafcc-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="bafcc-124">Diese Auflistung eignet sich eher für die Freigabe einfacher Daten zwischen den Designern und dem Host anstatt für die Freigabe komplexer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="bafcc-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="bafcc-125">EditingContext-Hostelemente und -Dienste</span><span class="sxs-lookup"><span data-stu-id="bafcc-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="bafcc-126">.NET Framework bietet eine Reihe von integrierten Elementen und Diensten, die über den Bearbeitungskontext zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="bafcc-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="bafcc-127">Elemente:</span><span class="sxs-lookup"><span data-stu-id="bafcc-127">Items:</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem><span data-ttu-id="bafcc-128">: Verwaltet die Liste der lokalen Assemblys verwiesen wird, die innerhalb des Workflows für Steuerelemente (z. B. den Ausdrucks-Editor) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bafcc-128">: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState><span data-ttu-id="bafcc-129">: Gibt an, ob der Designer einen schreibgeschützten Zustand aufweist.</span><span class="sxs-lookup"><span data-stu-id="bafcc-129">: Indicates whether the designer is in a read-only state.</span></span>  
  
-   <xref:System.Activities.Presentation.View.Selection><span data-ttu-id="bafcc-130">: Definiert die Auflistung von Objekten, die derzeit ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="bafcc-130">: Defines the collection of objects that are currently selected.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem><span data-ttu-id="bafcc-131">:</span><span class="sxs-lookup"><span data-stu-id="bafcc-131">:</span></span>  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem><span data-ttu-id="bafcc-132">: Enthält Informationen über die Datei, die die aktuelle bearbeitungssitzung basiert.</span><span class="sxs-lookup"><span data-stu-id="bafcc-132">: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="bafcc-133">Dienste:</span><span class="sxs-lookup"><span data-stu-id="bafcc-133">Services:</span></span>  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService><span data-ttu-id="bafcc-134">: Eigenschaften der aktuellen Instanz hinzugefügt werden können mithilfe von <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="bafcc-134">: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.View.DesignerView><span data-ttu-id="bafcc-135">: Ermöglicht den Zugriff auf die Eigenschaften des designercanvases.</span><span class="sxs-lookup"><span data-stu-id="bafcc-135">: Allows access to the properties of the designer canvas.</span></span>  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService><span data-ttu-id="bafcc-136">: Können den Inhalt der Toolbox auf die aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="bafcc-136">: Allows the contents of the toolbox to be updated.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService><span data-ttu-id="bafcc-137">: Verwendet, um Designerbefehle (z. B. Kontextmenü) in benutzerdefinierte dienstimplementierungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="bafcc-137">: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView><span data-ttu-id="bafcc-138">: Stellt Funktionen für den Debugger des Designers.</span><span class="sxs-lookup"><span data-stu-id="bafcc-138">: Provides functionality for the designer debugger.</span></span>  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService><span data-ttu-id="bafcc-139">: Bietet Zugriff auf das Dialogfeld "Ausdrucks-Editor".</span><span class="sxs-lookup"><span data-stu-id="bafcc-139">: Provides access to the Expression Editor dialog.</span></span>  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService><span data-ttu-id="bafcc-140">: Den Designer bietet integrierte Hilfefunktionen.</span><span class="sxs-lookup"><span data-stu-id="bafcc-140">: Provides the designer with integrated help functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService><span data-ttu-id="bafcc-141">: Ermöglicht den Zugriff auf Validierungsfehler mithilfe <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="bafcc-141">: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService><span data-ttu-id="bafcc-142">: Stellt einen internen Dienst zum Speichern und Abrufen von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="bafcc-142">: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="bafcc-143">Dieser Dienst wird von .NET Framework intern verwendet und ist nicht für die externe Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="bafcc-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService><span data-ttu-id="bafcc-144">: Ermöglicht den Zugriff auf die XAML Load Fehler Auflistung mit <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="bafcc-144">: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ModelService><span data-ttu-id="bafcc-145">: Vom Designer verwendet, um das Modell des bearbeiteten Workflows zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="bafcc-145">: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager><span data-ttu-id="bafcc-146">: Bietet Zugriff auf den Stamm des Modells Element Struktur mit <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span><span class="sxs-lookup"><span data-stu-id="bafcc-146">: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.UndoEngine><span data-ttu-id="bafcc-147">: Bietet rückgängig und wiederholen Sie die Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="bafcc-147">: Provides undo and redo functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ViewService><span data-ttu-id="bafcc-148">: Ordnet zugrunde liegenden Modellelementen visuelle Elemente.</span><span class="sxs-lookup"><span data-stu-id="bafcc-148">: Maps visual elements to underlying model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.ViewStateService><span data-ttu-id="bafcc-149">: Speichert Ansichtszustände für Modellelemente.</span><span class="sxs-lookup"><span data-stu-id="bafcc-149">: Stores view states for model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService><span data-ttu-id="bafcc-150">: Verwendet, um das Verhalten der virtueller Container-Benutzeroberfläche anpassen.</span><span class="sxs-lookup"><span data-stu-id="bafcc-150">: Used to customize the virtual container UI behavior.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService><span data-ttu-id="bafcc-151">: Verwendet, um die an- und Abmelden von Delegaten für ereignisbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="bafcc-151">: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="bafcc-152">Ermöglicht auch das Festlegen eines Fensterbesitzers.</span><span class="sxs-lookup"><span data-stu-id="bafcc-152">Also allows a window owner to be set.</span></span>
