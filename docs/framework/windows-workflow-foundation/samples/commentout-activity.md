---
title: "CommentOut-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e66d1383c42310c2f61b0b3059cb8b347ad55a15
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="commentout-activity"></a>CommentOut-Aktivität
Dieses Beispiel veranschaulicht, wie eine benutzerdefinierte Aktivität geschrieben wird, die andere Aktivitäten vom Ausführungspfad entfernt, indem sie effektiv auskommentiert werden.  
  
## <a name="the-commentout-activity"></a>Die CommentOut-Aktivität  
 Hierzu leitet sich die CommentOut-Aktivität von der <xref:System.Activities.CodeActivity>-Basisklasse ab und implementiert eine leere <xref:System.Activities.CodeActivity.Execute%2A>-Methode.  
  
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
  
 Das `Designer`-Attribut gibt die Klasse an, die zur Entwurfszeit die grafische Schnittstelle der Aktivität implementiert. Das `ContentProperty`-Attribut deklariert, dass die `"Body"`-Eigenschaft in der XAML-Darstellung einer Instanz dieser Aktivität übersprungen werden kann.  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 In der Designerklasse wird XAML verwendet, um eine benutzerdefinierte visuelle Darstellung der Aktivität zu erstellen. <xref:System.Activities.Presentation.WorkflowItemPresenter> ist eine Klasse, die den visuellen Editor bereitstellt.  
  
 Eine einzelne Aktivität kann auf der Oberfläche der `CommentOut`-Aktivität abgelegt werden. Wenn Sie dieser Oberfläche mehrere Aktivitäten hinzufügen möchten, fügen Sie zunächst eine Sequenzaktivität hinzu.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie "CommentOut.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Kompilieren Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Starten Sie das Beispiel ohne Debugging, indem Sie STRG+F5 drücken.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
