---
title: "CommentOut-Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# CommentOut-Aktivit&#228;t
Dieses Beispiel veranschaulicht, wie eine benutzerdefinierte Aktivität geschrieben wird, die andere Aktivitäten vom Ausführungspfad entfernt, indem sie effektiv auskommentiert werden.  
  
## Die CommentOut\-Aktivität  
 Hierzu leitet sich die CommentOut\-Aktivität von der <xref:System.Activities.CodeActivity>\-Basisklasse ab und implementiert eine leere <xref:System.Activities.CodeActivity.Execute%2A>\-Methode.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 Die Klasse wird wie im folgenden Beispiel gezeigt deklariert.  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
  
```  
  
 Das `Designer`\-Attribut gibt die Klasse an, die zur Entwurfszeit die grafische Schnittstelle der Aktivität implementiert.Das `ContentProperty`\-Attribut deklariert, dass die `“Body”`\-Eigenschaft in der XAML\-Darstellung einer Instanz dieser Aktivität übersprungen werden kann.  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 In der Designerklasse wird XAML verwendet, um eine benutzerdefinierte grafische Darstellung der Aktivität zu erstellen.<xref:System.Activities.Presentation.WorkflowItemPresenter> ist eine Klasse, die den grafischen Editor bereitstellt.  
  
 Eine einzelne Aktivität kann auf der Oberfläche der `CommentOut`\-Aktivität abgelegt werden.Wenn Sie dieser Oberfläche mehrere Aktivitäten hinzufügen möchten, fügen Sie zunächst eine Sequenzaktivität hinzu.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie "CommentOut.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Kompilieren Sie die Projektmappe, indem Sie STRG\+UMSCHALT\+B drücken.  
  
3.  Starten Sie das Beispiel ohne Debugging, indem Sie STRG\+F5 drücken.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`