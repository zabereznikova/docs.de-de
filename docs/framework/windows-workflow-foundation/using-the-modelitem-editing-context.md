---
title: Verwenden des ModelItem-Bearbeitungskontexts
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: 2ab002f902833d3b1a69ea0b03b5ca589f4492d1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275969"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="b380d-102">Verwenden des ModelItem-Bearbeitungskontexts</span><span class="sxs-lookup"><span data-stu-id="b380d-102">Using the ModelItem Editing Context</span></span>

<span data-ttu-id="b380d-103">Der <xref:System.Activities.Presentation.Model.ModelItem>-Bearbeitungskontext ist das Objekt, mit dem die Hostanwendung mit dem Designer kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="b380d-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <span data-ttu-id="b380d-104"><xref:System.Activities.Presentation.EditingContext> macht die beiden Methoden <xref:System.Activities.Presentation.EditingContext.Items%2A> und <xref:System.Activities.Presentation.EditingContext.Services%2A> verfügbar, die verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b380d-104"><xref:System.Activities.Presentation.EditingContext> exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="b380d-105">Items-Auflistung</span><span class="sxs-lookup"><span data-stu-id="b380d-105">The Items collection</span></span>  

 <span data-ttu-id="b380d-106">Die <xref:System.Activities.Presentation.EditingContext.Items%2A>-Auflistung wird verwendet, um auf Daten zuzugreifen, die zwischen dem Host und dem Designer freigegeben werden oder die in allen Designern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="b380d-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="b380d-107">Diese Auflistung verfügt über die folgenden Funktionen, auf die über die <xref:System.Activities.Presentation.ContextItemManager>-Klasse zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="b380d-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="b380d-108">Services-Auflistung</span><span class="sxs-lookup"><span data-stu-id="b380d-108">The Services collection</span></span>  

 <span data-ttu-id="b380d-109">Die <xref:System.Activities.Presentation.EditingContext.Services%2A>-Auflistung wird verwendet, um auf Dienste zuzugreifen, mit denen der Designer mit dem Host interagiert oder die von allen Designern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b380d-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="b380d-110">Diese Auflistung verfügt über die folgenden relevanten Methoden:</span><span class="sxs-lookup"><span data-stu-id="b380d-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="b380d-111">Zuweisen einer Aktivität zu einem Designer</span><span class="sxs-lookup"><span data-stu-id="b380d-111">Assigning a designer an activity</span></span>  

 <span data-ttu-id="b380d-112">Um anzugeben, welchen Designer eine Aktivität verwendet, wird das Designer-Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="b380d-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="b380d-113">Erstellen eines Diensts</span><span class="sxs-lookup"><span data-stu-id="b380d-113">Creating a service</span></span>  

 <span data-ttu-id="b380d-114">Zum Erstellen eines Diensts, der als Informationskanal zwischen dem Designer und dem Host agiert, müssen eine Schnittstelle und eine Implementierung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b380d-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="b380d-115">Die Schnittstelle wird von der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode verwendet, um die Member des Diensts zu definieren. Die Implementierung enthält die Logik für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b380d-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="b380d-116">Im folgenden Codebeispiel werden eine Dienstschnittstelle und eine Implementierung erstellt.</span><span class="sxs-lookup"><span data-stu-id="b380d-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```csharp  
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
  
## <a name="publishing-a-service"></a><span data-ttu-id="b380d-117">Veröffentlichen eines Diensts</span><span class="sxs-lookup"><span data-stu-id="b380d-117">Publishing a service</span></span>  

 <span data-ttu-id="b380d-118">Damit ein Designer einen Dienst nutzt, muss dieser zuerst vom Host mit der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="b380d-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="b380d-119">Abonnieren eines Diensts</span><span class="sxs-lookup"><span data-stu-id="b380d-119">Subscribing to a service</span></span>  

 <span data-ttu-id="b380d-120">Der Designer erhält mithilfe der <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>-Methode in der <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>-Methode Zugriff auf den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b380d-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="b380d-121">Der folgende Codeausschnitt veranschaulicht, wie ein Dienst abonniert wird.</span><span class="sxs-lookup"><span data-stu-id="b380d-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```csharp  
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
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="b380d-122">Freigeben von Daten mithilfe der Items-Auflistung</span><span class="sxs-lookup"><span data-stu-id="b380d-122">Sharing data using the Items collection</span></span>  

 <span data-ttu-id="b380d-123">Das Verwenden der Items-Auflistung ähnelt der Verwendung der Services-Auflistung, außer dass <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> anstelle von "Publish" verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b380d-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="b380d-124">Diese Auflistung eignet sich eher für die Freigabe einfacher Daten zwischen den Designern und dem Host anstatt für die Freigabe komplexer Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b380d-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="b380d-125">EditingContext-Hostelemente und -Dienste</span><span class="sxs-lookup"><span data-stu-id="b380d-125">EditingContext host items and services</span></span>  

 <span data-ttu-id="b380d-126">Der .NET Framework bietet eine Reihe integrierter Elemente und Dienste, auf die über den Bearbeitungs Kontext zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b380d-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="b380d-127">Elemente:</span><span class="sxs-lookup"><span data-stu-id="b380d-127">Items:</span></span>  
  
- <span data-ttu-id="b380d-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Verwaltet die Liste der lokalen Assemblys, auf die verwiesen wird und die im Workflow für Steuerelemente (z. B. Ausdrucks-Editor) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b380d-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
- <span data-ttu-id="b380d-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Gibt an, ob der Designer einen schreibgeschützten Zustand aufweist.</span><span class="sxs-lookup"><span data-stu-id="b380d-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indicates whether the designer is in a read-only state.</span></span>  
  
- <span data-ttu-id="b380d-130"><xref:System.Activities.Presentation.View.Selection>: Definiert die Auflistung der derzeit ausgewählten Objekte.</span><span class="sxs-lookup"><span data-stu-id="b380d-130"><xref:System.Activities.Presentation.View.Selection>: Defines the collection of objects that are currently selected.</span></span>  
  
- <span data-ttu-id="b380d-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span><span class="sxs-lookup"><span data-stu-id="b380d-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span></span>  
  
- <span data-ttu-id="b380d-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Stellt Informationen zur Datei bereit, auf der die aktuelle Bearbeitungssitzung basiert.</span><span class="sxs-lookup"><span data-stu-id="b380d-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="b380d-133">Dienste:</span><span class="sxs-lookup"><span data-stu-id="b380d-133">Services:</span></span>  
  
- <span data-ttu-id="b380d-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Erlaubt das Hinzufügen von Eigenschaften zur aktuellen Instanz mithilfe von <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="b380d-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
- <span data-ttu-id="b380d-135"><xref:System.Activities.Presentation.View.DesignerView>: Ermöglicht den Zugriff auf die Eigenschaften des Designercanvases.</span><span class="sxs-lookup"><span data-stu-id="b380d-135"><xref:System.Activities.Presentation.View.DesignerView>: Allows access to the properties of the designer canvas.</span></span>  
  
- <span data-ttu-id="b380d-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Ermöglicht die Aktualisierung des Inhalts der Toolbox.</span><span class="sxs-lookup"><span data-stu-id="b380d-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Allows the contents of the toolbox to be updated.</span></span>  
  
- <span data-ttu-id="b380d-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Wird verwendet, um Designerbefehle (z. B. Kontextmenü) in benutzerdefinierte Dienstimplementierungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="b380d-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
- <span data-ttu-id="b380d-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Stellt Funktionen für den Debugger des Designers bereit.</span><span class="sxs-lookup"><span data-stu-id="b380d-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Provides functionality for the designer debugger.</span></span>  
  
- <span data-ttu-id="b380d-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Bietet Zugriff auf das Dialogfeld "Ausdrucks-Editor".</span><span class="sxs-lookup"><span data-stu-id="b380d-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Provides access to the Expression Editor dialog.</span></span>  
  
- <span data-ttu-id="b380d-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Stellt integrierte Hilfefunktionen für den Designer bereit.</span><span class="sxs-lookup"><span data-stu-id="b380d-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Provides the designer with integrated help functionality.</span></span>  
  
- <span data-ttu-id="b380d-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Bietet mithilfe von <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> Zugriff auf Validierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="b380d-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
- <span data-ttu-id="b380d-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Stellt einen internen Dienst zum Speichern und Abrufen von Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="b380d-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="b380d-143">Dieser Dienst wird intern vom .NET Framework verwendet und ist nicht für die externe Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b380d-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
- <span data-ttu-id="b380d-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Bietet mithilfe von <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A> Zugriff auf die XAML-Ladefehlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="b380d-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
- <span data-ttu-id="b380d-145"><xref:System.Activities.Presentation.Services.ModelService>: Wird vom Designer verwendet, um mit dem Modell des bearbeiteten Workflows zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="b380d-145"><xref:System.Activities.Presentation.Services.ModelService>: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
- <span data-ttu-id="b380d-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Bietet mithilfe von <xref:System.Activities.Presentation.Model.ModelItem.Root%2A> Zugriff auf den Stamm der Modellelementstruktur.</span><span class="sxs-lookup"><span data-stu-id="b380d-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
- <span data-ttu-id="b380d-147"><xref:System.Activities.Presentation.UndoEngine>: Stellt Funktionen zum Rückgängigmachen und Wiederholen bereit.</span><span class="sxs-lookup"><span data-stu-id="b380d-147"><xref:System.Activities.Presentation.UndoEngine>: Provides undo and redo functionality.</span></span>  
  
- <span data-ttu-id="b380d-148"><xref:System.Activities.Presentation.Services.ViewService>: Ordnet den zugrunde liegenden Modellelementen visuelle Elemente zu.</span><span class="sxs-lookup"><span data-stu-id="b380d-148"><xref:System.Activities.Presentation.Services.ViewService>: Maps visual elements to underlying model items.</span></span>  
  
- <span data-ttu-id="b380d-149"><xref:System.Activities.Presentation.View.ViewStateService>: Speichert Ansichtszustände für Modellelemente.</span><span class="sxs-lookup"><span data-stu-id="b380d-149"><xref:System.Activities.Presentation.View.ViewStateService>: Stores view states for model items.</span></span>  
  
- <span data-ttu-id="b380d-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Wird verwendet, um das Verhalten der Benutzeroberfläche des virtuellen Containers anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b380d-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Used to customize the virtual container UI behavior.</span></span>  
  
- <span data-ttu-id="b380d-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Wird verwendet, um Delegaten für Ereignisbenachrichtigungen zu registrieren und die Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="b380d-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="b380d-152">Ermöglicht auch das Festlegen eines Fensterbesitzers.</span><span class="sxs-lookup"><span data-stu-id="b380d-152">Also allows a window owner to be set.</span></span>
