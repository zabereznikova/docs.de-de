---
title: CommentOut-Aktivität
ms.date: 03/30/2017
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
ms.openlocfilehash: 7847f4e1d77c2927a27be6b83f4016a22e4e3b32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
