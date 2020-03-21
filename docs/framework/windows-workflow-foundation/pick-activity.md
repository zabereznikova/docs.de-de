---
title: Auswahlaktivität
ms.date: 03/30/2017
ms.assetid: b3e49b7f-0285-4720-8c09-11ae18f0d53e
ms.openlocfilehash: 672de5fd3df5e8dde6c54118503bf2a11353b116
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182893"
---
# <a name="pick-activity"></a>Auswahlaktivität
Die <xref:System.Activities.Statements.Pick>-Aktivität vereinfacht die Modellierung einer Gruppe von Ereignistriggern gefolgt von den entsprechenden Handlern.  Eine <xref:System.Activities.Statements.Pick>-Aktivität enthält eine Auflistung von <xref:System.Activities.Statements.PickBranch>-Aktivitäten, wobei jedes <xref:System.Activities.Statements.PickBranch>-Objekt eine Paarung einer <xref:System.Activities.Statements.PickBranch.Trigger%2A>-Aktivität und einer <xref:System.Activities.Statements.PickBranch.Action%2A>-Aktivität darstellt.  Bei der Ausführung werden die Trigger für alle Branches parallel ausgeführt.  Nach Abschluss eines Triggers wird die zugeordnete Aktion ausgeführt, und alle anderen Trigger werden abgebrochen.  Das Verhalten [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <xref:System.Activities.Statements.Pick> der Aktivität ähnelt der .NET <xref:System.Workflow.Activities.ListenActivity> Framework 3.5-Aktivität.  
  
 Der folgende Screenshot aus dem SDK-Beispiel [Verwenden der Pick-Aktivität](./samples/using-the-pick-activity.md) zeigt eine Pick-Aktivität mit zwei Branches.  Ein Branch verfügt über einen Trigger mit dem Namen **Read input**, eine benutzerdefinierte Aktivität, die Eingaben aus der Befehlszeile liest. Der zweite Branch verfügt über einen <xref:System.Activities.Statements.Delay>-Aktivitätstrigger. Wenn die **Eingabeaktivität Lesen** <xref:System.Activities.Statements.Delay> Daten empfängt, bevor die Aktivität abgeschlossen ist, <xref:System.Activities.Statements.Delay> wird die Verzögerung abgebrochen, und eine Begrüßung wird an die Konsole geschrieben.  Die Aktivität **Read input** wird jedoch abgebrochen und eine Timeoutmeldung in die Konsole geschrieben, wenn die Aktivität in der zugewiesenen Zeit keine Daten empfängt.  Dies ist ein allgemeines Muster, mit dem einer beliebigen Aktion ein Timeoutverhalten hinzugefügt werden kann.  
  
 ![Auswahlaktivität](./media/pick-activity/pick-activity-two-branches.jpg)  
  
## <a name="best-practices"></a>Bewährte Methoden  
 Bei Verwendung der Pick-Option ist die ausgeführte Verzweigung diejenige, deren Trigger zuerst abgeschlossen wird.  Vom Konzept her werden alle Trigger parallel ausgeführt. Ein Trigger hat möglicherweise den Großteil seiner Logik ausgeführt, bevor er durch den Abschluss eines anderen Triggers abgebrochen wird.  Unter Beachtung dieser Option gilt als allgemeine Richtlinie für die Verwendung einer Pick-Aktivität, dass der Trigger als Einzelereignis behandelt werden sollte und so wenig Logik wie möglich enthalten sein sollte.  Im Idealfall enthält der Trigger gerade genügend Logik, um ein Ereignis empfangen zu können. Die gesamte Verarbeitung des Ereignisses sollte in der Aktion der Verzweigung erfolgen.  Auf diese Weise kann der Grad der Überschneidung bei der Ausführung der Trigger minimiert werden.  Nehmen Sie z. B. ein <xref:System.Activities.Statements.Pick>-Objekt mit zwei Triggern an, wobei jeder Trigger eine <xref:System.ServiceModel.Activities.Receive>-Aktivität und darauf folgend zusätzliche Logik enthält.  Wenn die zusätzliche Logik einen Leerlaufpunkt einführt, können beide <xref:System.ServiceModel.Activities.Receive>-Aktivitäten erfolgreich abgeschlossen werden.  Ein Trigger wird vollständig abgeschlossen, während ein anderer nur teilweise abgeschlossen wird.  In einigen Szenarien ist es nicht zulässig, dass eine Meldung angenommen und die Verarbeitung nur teilweise abgeschlossen wird.  Wenn daher die integrierten WF-Messagingaktivitäten wie <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> verwendet, während <xref:System.ServiceModel.Activities.Receive> häufig im Trigger verwendet wird, sollten das <xref:System.ServiceModel.Activities.SendReply>-Objekt und andere Logik nach Möglichkeit der Aktion hinzugefügt werden.  
  
## <a name="using-the-pick-activity-in-the-designer"></a>Verwenden der Pick-Aktivität im Designer  
 Um die Pick-Aktivität im Designer verwenden zu können, suchen Sie in der Toolbox nach **Pick** und **PickBranch**.  Ziehen Sie **Pick** per Drag & Drop auf die Canvas.  Standardmäßig enthält eine neue **Pick**-Aktivität im Designer zwei Branches.  Um zusätzliche Branches hinzuzufügen, ziehen Sie die **PickBranch**-Aktivität per Drag & Drop neben vorhandene Branches. Aktivitäten können für die **Pick**-Aktivität entweder im Bereich **Trigger** oder im Bereich **Aktion** einer **PickBranch** abgelegt werden.  
  
## <a name="using-the-pick-activity-in-code"></a>Verwenden der Pick-Aktivität im Code  
 Die <xref:System.Activities.Statements.Pick>-Aktivität wird verwendet, indem die zugehörige <xref:System.Activities.Statements.Pick.Branches%2A>-Auflistung mit <xref:System.Activities.Statements.PickBranch>-Aktivitäten aufgefüllt wird. Die <xref:System.Activities.Statements.PickBranch>-Aktivitäten verfügen jeweils über eine <xref:System.Activities.Statements.PickBranch.Trigger%2A>-Eigenschaft des Typs <xref:System.Activities.Activity>. Wenn die Ausführung der angegebenen Aktivität abgeschlossen wird, wird die <xref:System.Activities.Statements.PickBranch.Action%2A> ausgeführt.  
  
 Im folgenden Codebeispiel wird demonstriert, wie mit einer <xref:System.Activities.Statements.Pick>-Aktivität ein Timeout für eine Aktivität implementiert wird, die eine Zeile aus der Konsole liest.  
  
```csharp  
Sequence body = new Sequence()  
{  
    Variables = { name },  
    Activities =
   {  
       new System.Activities.Statements.Pick  
        {  
           Branches =
           {  
               new PickBranch  
               {  
                   Trigger = new ReadLine  
                   {  
                      Result = name,  
                      BookmarkName = "name"  
                   },  
                   Action = new WriteLine
                   {
                       Text = ExpressionServices.Convert<string>(ctx => "Hello " +
                           name.Get(ctx))
                   }  
               },  
               new PickBranch  
               {  
                   Trigger = new Delay  
                   {  
                      Duration = new TimeSpan(0, 0, 5)  
                   },  
                   Action = new WriteLine  
                   {  
                      Text = "Time is up."  
                   }  
               }  
           }  
       }  
   }  
};  
```  
  
```xaml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:String" Name="username" />  
  </Sequence.Variables>  
  <Pick>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <ReadLine BookmarkName="name" Result="username" />  
      </PickBranch.Trigger>  
      <WriteLine>[String.Concat("Hello ", username)]</WriteLine>  
    </PickBranch>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <Delay>00:00:05</Delay>  
      </PickBranch.Trigger>  
      <WriteLine>Time is up.</WriteLine>  
    </PickBranch>  
  </Pick>  
</Sequence>  
```
