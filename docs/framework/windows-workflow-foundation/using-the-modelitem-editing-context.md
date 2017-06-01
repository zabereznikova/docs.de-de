---
title: "Verwenden des ModelItem-Bearbeitungskontexts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Verwenden des ModelItem-Bearbeitungskontexts
Der <xref:System.Activities.Presentation.Model.ModelItem>\-Bearbeitungskontext ist das Objekt, mit dem die Hostanwendung mit dem Designer kommuniziert.<xref:System.Activities.Presentation.EditingContext> macht die beiden verwendbaren Methoden <xref:System.Activities.Presentation.EditingContext.Items%2A> und <xref:System.Activities.Presentation.EditingContext.Services%2A> verfügbar.  
  
## Items\-Auflistung  
 Die <xref:System.Activities.Presentation.EditingContext.Items%2A>\-Auflistung wird verwendet, um auf Daten zuzugreifen, die zwischen dem Host und dem Designer freigegeben werden oder die in allen Designern zur Verfügung stehen.Diese Auflistung verfügt über die folgenden Funktionen, auf die über die <xref:System.Activities.Presentation.ContextItemManager>\-Klasse zugegriffen werden kann:  
  
1.  <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2.  <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## Services\-Auflistung  
 Die <xref:System.Activities.Presentation.EditingContext.Services%2A>\-Auflistung wird verwendet, um auf Dienste zuzugreifen, mit denen der Designer mit dem Host interagiert oder die von allen Designern verwendet werden.Diese Auflistung verfügt über die folgenden relevanten Methoden:  
  
1.  <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2.  <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## Zuweisen einer Aktivität zu einem Designer  
 Um anzugeben, welchen Designer eine Aktivität verwendet, wird das Designer\-Attribut verwendet.  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
  
```  
  
## Erstellen eines Diensts  
 Zum Erstellen eines Diensts, der als Informationskanal zwischen dem Designer und dem Host agiert, müssen eine Schnittstelle und eine Implementierung erstellt werden.Die Schnittstelle wird von der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>\-Methode verwendet, um die Member des Diensts zu definieren. Die Implementierung enthält die Logik für den Dienst.Im folgenden Codebeispiel werden eine Dienstschnittstelle und eine Implementierung erstellt.  
  
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
  
## Veröffentlichen eines Diensts  
 Damit ein Designer einen Dienst nutzt, muss dieser zuerst vom Host mit der <xref:System.Activities.Presentation.ServiceManager.Publish%2A>\-Methode veröffentlicht werden.  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## Abonnieren eines Diensts  
 Der Designer erhält mithilfe der <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>\-Methode in der <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>\-Methode Zugriff auf den Dienst.Der folgende Codeausschnitt veranschaulicht, wie ein Dienst abonniert wird.  
  
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
  
## Freigeben von Daten mithilfe der Items\-Auflistung  
 Das Verwenden der Items\-Auflistung ähnelt der Verwendung der Services\-Auflistung, außer dass <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> anstelle von "Publish" verwendet wird.Diese Auflistung eignet sich eher für die Freigabe einfacher Daten zwischen den Designern und dem Host anstatt für die Freigabe komplexer Funktionen.  
  
## EditingContext\-Hostelemente und \-Dienste  
 .NET Framework stellt eine Reihe von integrierten Elementen und Diensten bereit, auf die über den Bearbeitungskontext zugegriffen wird.  
  
 Elemente:  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Verwaltet die Liste der lokalen Assemblys, auf die verwiesen wird und die im Workflow für Steuerelemente \(z. B. Ausdrucks\-Editor\) verwendet werden.  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Gibt an, ob der Designer einen schreibgeschützten Zustand aufweist.  
  
-   <xref:System.Activities.Presentation.View.Selection>: Definiert die Auflistung der derzeit ausgewählten Objekte.  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem>: Stellt Informationen zur Datei bereit, auf der die aktuelle Bearbeitungssitzung basiert.  
  
 Dienste:  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Erlaubt das Hinzufügen von Eigenschaften zur aktuellen Instanz mithilfe von <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
-   <xref:System.Activities.Presentation.View.DesignerView>: Ermöglicht den Zugriff auf die Eigenschaften des Designercanvases.  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService>: Ermöglicht die Aktualisierung des Inhalts der Toolbox.  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService>: Wird verwendet, um Designerbefehle \(z. B. Kontextmenü\) in benutzerdefinierte Dienstimplementierungen zu integrieren.  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Stellt Funktionen für den Debugger des Designers bereit.  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService>: Bietet Zugriff auf das Dialogfeld "Ausdrucks\-Editor".  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService>: Stellt integrierte Hilfefunktionen für den Designer bereit.  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService>: Bietet mithilfe von <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> Zugriff auf Validierungsfehler.  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Stellt einen internen Dienst zum Speichern und Abrufen von Daten bereit.Dieser Dienst wird von .NET Framework intern verwendet und ist nicht für die externe Verwendung vorgesehen.  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService>: Bietet mithilfe von <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A> Zugriff auf die XAML\-Ladefehlerauflistung.  
  
-   <xref:System.Activities.Presentation.Services.ModelService>: Wird vom Designer verwendet, um mit dem Modell des bearbeiteten Workflows zu interagieren.  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager>: Bietet mithilfe von <xref:System.Activities.Presentation.Model.ModelItem.Root%2A> Zugriff auf den Stamm der Modellelementstruktur.  
  
-   <xref:System.Activities.Presentation.UndoEngine>: Stellt Funktionen zum Rückgängigmachen und Wiederholen bereit.  
  
-   <xref:System.Activities.Presentation.Services.ViewService>: Ordnet den zugrunde liegenden Modellelementen visuelle Elemente zu.  
  
-   <xref:System.Activities.Presentation.View.ViewStateService>: Speichert Ansichtszustände für Modellelemente.  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService>: Wird verwendet, um das Verhalten der Benutzeroberfläche des virtuellen Containers anzupassen.  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService>: Wird verwendet, um Delegaten für Ereignisbenachrichtigungen zu registrieren und die Registrierung aufzuheben.Ermöglicht auch das Festlegen eines Fensterbesitzers.