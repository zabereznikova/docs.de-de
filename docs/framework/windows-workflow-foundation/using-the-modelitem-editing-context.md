---
title: Verwenden des ModelItem-Bearbeitungskontexts
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a47cb53e50d221c0ae07cf0841688fe4f8ced7d4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988921"
---
# <a name="using-the-modelitem-editing-context"></a>Verwenden des ModelItem-Bearbeitungskontexts
Der <xref:System.Activities.Presentation.Model.ModelItem>-Bearbeitungskontext ist das Objekt, mit dem die Hostanwendung mit dem Designer kommuniziert. <xref:System.Activities.Presentation.EditingContext> macht die beiden Methoden <xref:System.Activities.Presentation.EditingContext.Items%2A> und <xref:System.Activities.Presentation.EditingContext.Services%2A> verfügbar, die verwendet werden können.  
  
## <a name="the-items-collection"></a>Items-Auflistung  
 Die <xref:System.Activities.Presentation.EditingContext.Items%2A>-Auflistung wird verwendet, um auf Daten zuzugreifen, die zwischen dem Host und dem Designer freigegeben werden oder die in allen Designern zur Verfügung stehen. Diese Auflistung verfügt über die folgenden Funktionen, auf die über die <xref:System.Activities.Presentation.ContextItemManager>-Klasse zugegriffen werden kann:  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a>Services-Auflistung  
 Die <xref:System.Activities.Presentation.EditingContext.Services%2A>-Auflistung wird verwendet, um auf Dienste zuzugreifen, mit denen der Designer mit dem Host interagiert oder die von allen Designern verwendet werden. Diese Auflistung verfügt über die folgenden relevanten Methoden:  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a>Zuweisen einer Aktivität zu einem Designer  
 Um anzugeben, welchen Designer eine Aktivität verwendet, wird das Designer-Attribut verwendet.  
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a>Erstellen eines Diensts  
 Zum Erstellen eines Diensts, der als Informationskanal zwischen dem Designer und dem Host agiert, müssen eine Schnittstelle und eine Implementierung erstellt werden. Die Schnittstelle wird von der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode verwendet, um die Member des Diensts zu definieren. Die Implementierung enthält die Logik für den Dienst. Im folgenden Codebeispiel werden eine Dienstschnittstelle und eine Implementierung erstellt.  
  
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
  
## <a name="publishing-a-service"></a>Veröffentlichen eines Diensts  
 Damit ein Designer einen Dienst nutzt, muss dieser zuerst vom Host mit der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode veröffentlicht werden.  
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Abonnieren eines Diensts  
 Der Designer erhält mithilfe der <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>-Methode in der <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>-Methode Zugriff auf den Dienst. Der folgende Codeausschnitt veranschaulicht, wie ein Dienst abonniert wird.  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a>Freigeben von Daten mithilfe der Items-Auflistung  
 Das Verwenden der Items-Auflistung ähnelt der Verwendung der Services-Auflistung, außer dass <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> anstelle von "Publish" verwendet wird. Diese Auflistung eignet sich eher für die Freigabe einfacher Daten zwischen den Designern und dem Host anstatt für die Freigabe komplexer Funktionen.  
  
## <a name="editingcontext-host-items-and-services"></a>EditingContext-Hostelemente und -Dienste  
 Der .NET Framework bietet eine Reihe integrierter Elemente und Dienste, auf die über den Bearbeitungs Kontext zugegriffen wird.  
  
 Elemente:  
  
- <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Verwaltet die Liste der referenzierten lokalen Assemblys, die im Workflow für Steuerelemente verwendet werden (z. b. den Ausdrucks-Editor).  
  
- <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Gibt an, ob der Designer einen schreibgeschützten Zustand aufweist.  
  
- <xref:System.Activities.Presentation.View.Selection>: Definiert die Auflistung von-Objekten, die derzeit ausgewählt sind.  
  
- <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
- <xref:System.Activities.Presentation.WorkflowFileItem>: Stellt Informationen zu der Datei bereit, auf der die aktuelle Bearbeitungs Sitzung basiert.  
  
 Dienste:  
  
- <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Ermöglicht das Hinzufügen von Eigenschaften zur aktuellen Instanz mithilfe <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>von.  
  
- <xref:System.Activities.Presentation.View.DesignerView>: Ermöglicht den Zugriff auf die Eigenschaften der Designer Canvas.  
  
- <xref:System.Activities.Presentation.IActivityToolboxService>: Ermöglicht das Aktualisieren des Inhalts der Toolbox.  
  
- <xref:System.Activities.Presentation.Hosting.ICommandService>: Wird verwendet, um Designer Befehle (z. b. Kontextmenü) in benutzerdefinierte Dienst Implementierungen zu integrieren.  
  
- <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Stellt Funktionen für den Designer Debugger bereit.  
  
- <xref:System.Activities.Presentation.View.IExpressionEditorService>: Bietet Zugriff auf das Dialogfeld für den Ausdrucks-Editor.  
  
- <xref:System.Activities.Presentation.IIntegratedHelpService>: Stellt dem Designer integrierte Hilfefunktionen zur Verfügung.  
  
- <xref:System.Activities.Presentation.Validation.IValidationErrorService>: Ermöglicht den Zugriff auf Validierungs Fehler <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>mithilfe von.  
  
- <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Stellt einen internen Dienst zum Speichern und Abrufen von Daten bereit. Dieser Dienst wird intern vom .NET Framework verwendet und ist nicht für die externe Verwendung vorgesehen.  
  
- <xref:System.Activities.Presentation.IXamlLoadErrorService>: Ermöglicht den Zugriff auf die XAML-Ladefehler <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>Auflistung mithilfe von.  
  
- <xref:System.Activities.Presentation.Services.ModelService>: Wird vom Designer verwendet, um mit dem Modell des bearbeiteten Workflows zu interagieren.  
  
- <xref:System.Activities.Presentation.Model.ModelTreeManager>: Ermöglicht den Zugriff auf den Stamm der Modellelement Struktur mithilfe <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>von.  
  
- <xref:System.Activities.Presentation.UndoEngine>: Stellt Funktionen zum rückgängig und wiederholen bereit.  
  
- <xref:System.Activities.Presentation.Services.ViewService>: Ordnet den zugrunde liegenden Modellelementen visuelle Elemente zu.  
  
- <xref:System.Activities.Presentation.View.ViewStateService>: Speichert Ansichts Zustände für Modellelemente.  
  
- <xref:System.Activities.Presentation.View.VirtualizedContainerService>: Wird verwendet, um das Verhalten der Benutzeroberfläche des virtuellen Containers anzupassen.  
  
- <xref:System.Activities.Presentation.Hosting.WindowHelperService>: Wird verwendet, um Delegaten für Ereignis Benachrichtigungen zu registrieren und deren Registrierung aufzuheben. Ermöglicht auch das Festlegen eines Fensterbesitzers.
