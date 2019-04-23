---
title: Verwenden des ModelItem-Bearbeitungskontexts
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a2628bbbf2f6684e5d484b05cd5a2ac622f3b664
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296877"
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
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a>Erstellen eines Diensts  
 Zum Erstellen eines Diensts, der als Informationskanal zwischen dem Designer und dem Host agiert, müssen eine Schnittstelle und eine Implementierung erstellt werden. Die Schnittstelle wird von der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode verwendet, um die Member des Diensts zu definieren. Die Implementierung enthält die Logik für den Dienst. Im folgenden Codebeispiel werden eine Dienstschnittstelle und eine Implementierung erstellt.  
  
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
  
## <a name="publishing-a-service"></a>Veröffentlichen eines Diensts  
 Damit ein Designer einen Dienst nutzt, muss dieser zuerst vom Host mit der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>-Methode veröffentlicht werden.  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Abonnieren eines Diensts  
 Der Designer erhält mithilfe der <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>-Methode in der <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>-Methode Zugriff auf den Dienst. Der folgende Codeausschnitt veranschaulicht, wie ein Dienst abonniert wird.  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a>Freigeben von Daten mithilfe der Items-Auflistung  
 Das Verwenden der Items-Auflistung ähnelt der Verwendung der Services-Auflistung, außer dass <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> anstelle von "Publish" verwendet wird. Diese Auflistung eignet sich eher für die Freigabe einfacher Daten zwischen den Designern und dem Host anstatt für die Freigabe komplexer Funktionen.  
  
## <a name="editingcontext-host-items-and-services"></a>EditingContext-Hostelemente und -Dienste  
 .NET Framework bietet eine Reihe von integrierten Elementen und Diensten, die über den Bearbeitungskontext zugegriffen wird.  
  
 Elemente:  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Verwaltet die Liste der lokalen Assemblys verwiesen wird, die innerhalb des Workflows für Steuerelemente (z. B. den Ausdrucks-Editor) verwendet werden.  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Gibt an, ob der Designer einen schreibgeschützten Zustand aufweist.  
  
-   <xref:System.Activities.Presentation.View.Selection>: Definiert die Auflistung von Objekten, die derzeit ausgewählt sind.  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem>: Enthält Informationen über die Datei, die die aktuelle bearbeitungssitzung basiert.  
  
 Dienste:  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Eigenschaften der aktuellen Instanz hinzugefügt werden können mithilfe von <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
-   <xref:System.Activities.Presentation.View.DesignerView>: Ermöglicht den Zugriff auf die Eigenschaften des designercanvases.  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService>: Können den Inhalt der Toolbox auf die aktualisiert werden.  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService>: Verwendet, um Designerbefehle (z. B. Kontextmenü) in benutzerdefinierte dienstimplementierungen zu integrieren.  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Stellt Funktionen für den Debugger des Designers.  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService>: Bietet Zugriff auf das Dialogfeld "Ausdrucks-Editor".  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService>: Den Designer bietet integrierte Hilfefunktionen.  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService>: Ermöglicht den Zugriff auf Validierungsfehler mithilfe <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Stellt einen internen Dienst zum Speichern und Abrufen von Daten bereit. Dieser Dienst wird von .NET Framework intern verwendet und ist nicht für die externe Verwendung vorgesehen.  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService>: Ermöglicht den Zugriff auf die XAML Load Fehler Auflistung mit <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
-   <xref:System.Activities.Presentation.Services.ModelService>: Vom Designer verwendet, um das Modell des bearbeiteten Workflows zu interagieren.  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager>: Bietet Zugriff auf den Stamm des Modells Element Struktur mit <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
-   <xref:System.Activities.Presentation.UndoEngine>: Bietet rückgängig und wiederholen Sie die Funktionalität.  
  
-   <xref:System.Activities.Presentation.Services.ViewService>: Ordnet zugrunde liegenden Modellelementen visuelle Elemente.  
  
-   <xref:System.Activities.Presentation.View.ViewStateService>: Speichert Ansichtszustände für Modellelemente.  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService>: Verwendet, um das Verhalten der virtueller Container-Benutzeroberfläche anpassen.  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService>: Verwendet, um die an- und Abmelden von Delegaten für ereignisbenachrichtigungen. Ermöglicht auch das Festlegen eines Fensterbesitzers.
