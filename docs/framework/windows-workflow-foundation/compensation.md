---
title: Kompensierung
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: 60e2789c4bbd29185af50eaf6555307b894d3902
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289190"
---
# <a name="compensation"></a>Kompensierung

Kompensierung in Windows Workflow Foundation (WF) ist der Mechanismus, mit dem zuvor abgeschlossene Aufgaben rückgängig gemacht oder kompensiert werden können (gemäß der von der Anwendung definierten Logik), wenn ein nachfolgender Fehler auftritt. In diesem Abschnitt wird beschrieben, wie die Kompensation in Workflows verwendet wird.  
  
## <a name="compensation-vs-transactions"></a>Kompensation und Transaktionen  

 Eine Transaktion ermöglicht es Ihnen, mehrere Vorgänge in nur einer Arbeitseinheit zu kombinieren. Wenn Sie Transaktionen verwenden, kann Ihre Anwendung alle Änderungen zurücknehmen (Rollback), die innerhalb der Transaktion ausgeführt wurden, falls während des Transaktionsprozesses ein Fehler auftritt. Die Verwendung von Transaktionen eignet sich jedoch möglicherweise nicht für Arbeitsaufgaben mit langer Laufzeit. Angenommen, eine Anwendung zum Planen von Reisen wird als Workflow implementiert. Die Schritte des Workflows bestehen z. B. aus der Buchung eines Flugs, dem Warten auf die Genehmigung des Managers und der anschließenden Bezahlung des Flugs. Da sich dieser Prozess über mehrere Tage hinziehen kann, ist es nicht sinnvoll, die Buchungs- und Zahlungsschritte in derselben Transaktion zu implementieren. In einem Szenario wie diesem kann der Buchungsschritt des Workflows mittels Kompensation rückgängig gemacht werden, wenn an späterer Stelle ein Verarbeitungsfehler auftritt.  
  
> [!NOTE]
> Dieses Thema behandelt die Kompensation in Workflows. Weitere Informationen zu Transaktionen in Workflows finden Sie unter [Transaktionen](workflow-transactions.md) und <xref:System.Activities.Statements.TransactionScope> . Weitere Informationen zu Transaktionen finden Sie unter <xref:System.Transactions?displayProperty=nameWithType> und <xref:System.Transactions.Transaction?displayProperty=nameWithType> .  
  
## <a name="using-compensableactivity"></a>Verwenden von CompensableActivity  

 Das <xref:System.Activities.Statements.CompensableActivity>-Objekt ist die wichtigste Kompensationsaktivität in [!INCLUDE[wf1](../../../includes/wf1-md.md)]. Alle Aktivitäten zum Ausführen einer Arbeit, die möglicherweise kompensiert werden soll, werden in das <xref:System.Activities.Statements.CompensableActivity.Body%2A>-Element eines <xref:System.Activities.Statements.CompensableActivity>-Objekts eingefügt. In diesem Beispiel wird der Reservierungsschritt der Buchung eines Flugs in das <xref:System.Activities.Statements.CompensableActivity.Body%2A>-Element eines <xref:System.Activities.Statements.CompensableActivity>-Objekts eingefügt, und der Abbruch der Reservierung wird in das <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>-Element eingefügt. Im Workflow folgen unmittelbar auf das <xref:System.Activities.Statements.CompensableActivity>-Objekt zwei Aktivitäten, für die eine Genehmigung durch einen Manager erfolgen muss und die dann die Buchung des Flugs abschließen. Wenn der Workflow aufgrund eines Fehlers abgebrochen wird, nachdem das <xref:System.Activities.Statements.CompensableActivity>-Objekt erfolgreich abgeschlossen wurde, werden die Aktivitäten im <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>-Handler geplant und der Flug wird gestrichen.  
  
 [!code-csharp[CFX_CompensationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 Das folgende Beispiel ist der Workflow in XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.  
  
 **ReserveFlight: Ticket wird reserviert.**  
**ManagerApproval: die Genehmigung des Managers wurde empfangen.** 
 **Purchaseflight: Ticket wird gekauft.** 
 Der **Workflow wurde erfolgreich mit dem Status "geschlossen" abgeschlossen.**
> [!NOTE]
> Die Beispielaktivitäten in diesem Thema z. B. `ReserveFlight` geben ihren Namen und Zweck auf der Konsole an, um die Reihenfolge zu veranschaulichen, in der die Aktivitäten ausgeführt werden, wenn eine Kompensation auftritt.  
  
### <a name="default-workflow-compensation"></a>Standard-Workflowkompensation  

 Standardmäßig wird nach dem Abbruch eines Workflows die Kompensationslogik für jede kompensierbare Aktivität ausgeführt, die erfolgreich abgeschlossen wurde und noch nicht bestätigt oder kompensiert wurde.  
  
> [!NOTE]
> Wenn eine <xref:System.Activities.Statements.CompensableActivity> *bestätigt* wird, kann die Kompensierung für die Aktivität nicht mehr aufgerufen werden. Der Bestätigungsvorgang wird weiter unten in diesem Abschnitt beschrieben.  
  
 In diesem Beispiel wird eine Ausnahme ausgelöst, nachdem der Flug reserviert wurde und bevor der Genehmigungsschritt durch den Manager erfolgen konnte.  
  
 [!code-csharp[CFX_CompensationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 Dieses Beispiel ist der Workflow in XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:SimulatedErrorCondition />  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 [!code-csharp[CFX_CompensationExample#100](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#100)]  
  
 Wenn der Workflow aufgerufen wird, wird die simulierte Fehlerbedingungsausnahme von der Hostanwendung in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> behandelt, der Workflow wird abgebrochen, und die Kompensationslogik wird aufgerufen.  
  
 **ReserveFlight: Ticket wird reserviert.**  
**Simulatederrorcondition: Auslösen einer ApplicationException.** 
 **Nicht behandelte Workflow Ausnahme:** 
 **System. ApplicationException: simulierte Fehlerbedingung im Workflow.** 
 **Cancelflight: Ticket wird abgebrochen.** 
 **Workflow wurde erfolgreich mit dem Status "abgebrochen" abgeschlossen.**

### <a name="cancellation-and-compensableactivity"></a>Abbruch und CompensableActivity  

 Wenn die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.Body%2A> eines <xref:System.Activities.Statements.CompensableActivity>-Objekts nicht abgeschlossen wurden und die Aktivität abgebrochen wird, werden die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> ausgeführt.  
  
> [!NOTE]
> <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> wird nur aufgerufen, wenn die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.Body%2A> des <xref:System.Activities.Statements.CompensableActivity>-Objekts nicht abgeschlossen wurden und die Aktivität abgebrochen wird. <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> wird nur ausgeführt, wenn die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.Body%2A> des <xref:System.Activities.Statements.CompensableActivity>-Objekts erfolgreich abgeschlossen wurden, und die Kompensation wird anschließend für die Aktivität aufgerufen.  
  
 <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> gibt Workflowautoren die Gelegenheit, eine geeignete Abbruchlogik bereitzustellen. Im folgenden Beispiel wird eine Ausnahme während der Ausführung von <xref:System.Activities.Statements.CompensableActivity.Body%2A> ausgelöst, und dann wird <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> aufgerufen.  
  
```csharp  
Activity wf = new Sequence()  
{  
    Activities =  
    {  
        new CompensableActivity  
        {  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new ChargeCreditCard(),  
                    new SimulatedErrorCondition(),  
                    new ReserveFlight()  
                }  
            },  
            CompensationHandler = new CancelFlight(),  
            CancellationHandler = new CancelCreditCard()  
        },  
        new ManagerApproval(),  
        new PurchaseFlight()  
    }  
};  
```  
  
 Dieses Beispiel ist der Workflow in XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <Sequence>  
      <c:ChargeCreditCard />  
      <c:SimulatedErrorCondition />  
      <c:ReserveFlight />  
    </Sequence>  
    <CompensableActivity.CancellationHandler>  
      <c:CancelCreditCard />  
    </CompensableActivity.CancellationHandler>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 Wenn der Workflow aufgerufen wird, wird die simulierte Fehlerbedingungsausnahme von der Hostanwendung in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> behandelt, der Workflow wird abgebrochen, und die Abbruchlogik von <xref:System.Activities.Statements.CompensableActivity> wird aufgerufen. In diesem Beispiel haben die Kompensationslogik und die Abbruchlogik unterschiedliche Ziele. Wenn <xref:System.Activities.Statements.CompensableActivity.Body%2A> erfolgreich abgeschlossen wurde, bedeutet dies, dass die Kreditkarte belastet und der Flug gebucht wurde. Somit sollten von der Kompensation beide Schritte rückgängig gemacht werden. (In diesem Beispiel werden beim Abbrechen des Flugs die Kreditkartengebühren automatisch abgebrochen.) Wenn jedoch <xref:System.Activities.Statements.CompensableActivity> abgebrochen wird, bedeutet dies, <xref:System.Activities.Statements.CompensableActivity.Body%2A> dass nicht fertiggestellt wurde. Daher muss die Logik der in der <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> Lage sein, zu bestimmen, wie der Abbruch am besten behandelt werden soll. In diesem Beispiel wird die Kreditkartenbelastung durch <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> storniert. Da `ReserveFlight` jedoch die letzte Aktivität in <xref:System.Activities.Statements.CompensableActivity.Body%2A> war, wird nicht versucht, den Flug zu stornieren. `ReserveFlight` war die letzte Aktivität in <xref:System.Activities.Statements.CompensableActivity.Body%2A>. Wenn diese erfolgreich abgeschlossen worden wäre, wäre <xref:System.Activities.Statements.CompensableActivity.Body%2A> abgeschlossen worden und kein Abbruch möglich gewesen.  
  
 **ChargeCreditCard: Kreditkarte für Flug belasten.**  
**Simulatederrorcondition: Auslösen einer ApplicationException.** 
 **Nicht behandelte Workflow Ausnahme:** 
 **System. ApplicationException: simulierte Fehlerbedingung im Workflow.** 
 **Cancelcreditcard: Kreditkartengebühren werden abgebrochen.** 
 **Workflow wurde erfolgreich mit dem Status "abgebrochen" abgeschlossen.**  Weitere Informationen zu Abbruch finden Sie unter [Abbruch](modeling-cancellation-behavior-in-workflows.md).  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a>Explizite Kompensation mit Verwendung der Compensate-Aktivität  

 Im vorherigen Abschnitt wurde die implizite Kompensation behandelt. Eine implizite Kompensation eignet sich für einfache Szenarien. Wenn jedoch mehr explizite Steuerungsmöglichkeiten für das Planen der Kompensationsbehandlung erforderlich sind, kann die <xref:System.Activities.Statements.Compensate>-Aktivität verwendet werden. Um den Kompensationsprozess mit der <xref:System.Activities.Statements.Compensate>-Aktivität zu initiieren, wird das <xref:System.Activities.Statements.CompensationToken>-Objekt des <xref:System.Activities.Statements.CompensableActivity>-Objekts verwendet, für das eine Kompensation möglich sein soll. Mit der <xref:System.Activities.Statements.Compensate>-Aktivität kann eine Kompensation für ein beliebiges abgeschlossenes <xref:System.Activities.Statements.CompensableActivity>-Objekt initiiert werden, solange dieses nicht bestätigt oder kompensiert wurde. Beispielsweise kann eine <xref:System.Activities.Statements.Compensate>-Aktivität im Abschnitt <xref:System.Activities.Statements.TryCatch.Catches%2A> einer <xref:System.Activities.Statements.TryCatch>-Aktivität oder jederzeit nach Abschluss von <xref:System.Activities.Statements.CompensableActivity> verwendet werden. In diesem Beispiel wird die <xref:System.Activities.Statements.Compensate>-Aktivität im Abschnitt <xref:System.Activities.Statements.TryCatch.Catches%2A> einer <xref:System.Activities.Statements.TryCatch>-Aktivität dazu verwendet, die Aktion von <xref:System.Activities.Statements.CompensableActivity> rückgängig zu machen.  
  
 [!code-csharp[CFX_CompensationExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 Dieses Beispiel ist der Workflow in XAML.  
  
```xaml  
<TryCatch  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:s="clr-namespace:System;assembly=mscorlib"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <TryCatch.Variables>  
    <Variable  
       x:TypeArguments="CompensationToken"  
       x:Name="__ReferenceID0"  
       Name="token1" />  
  </TryCatch.Variables>  
  <TryCatch.Try>  
    <Sequence>  
      <CompensableActivity>  
        <CompensableActivity.Result>  
          <OutArgument  
             x:TypeArguments="CompensationToken">  
            <VariableReference  
               x:TypeArguments="CompensationToken"  
               Variable="{x:Reference __ReferenceID0}">  
              <VariableReference.Result>  
                <OutArgument  
                   x:TypeArguments="Location(CompensationToken)" />  
              </VariableReference.Result>  
            </VariableReference>  
          </OutArgument>  
        </CompensableActivity.Result>  
        <CompensableActivity.CompensationHandler>  
          <c:CancelFlight />  
        </CompensableActivity.CompensationHandler>  
        <CompensableActivity.ConfirmationHandler>  
          <c:ConfirmFlight />  
        </CompensableActivity.ConfirmationHandler>  
        <c:ReserveFlight />  
      </CompensableActivity>  
      <c:SimulatedErrorCondition />  
      <c:ManagerApproval />  
      <c:PurchaseFlight />  
    </Sequence>  
  </TryCatch.Try>  
  <TryCatch.Catches>  
    <Catch  
       x:TypeArguments="s:ApplicationException">  
      <ActivityAction  
         x:TypeArguments="s:ApplicationException">  
        <Compensate>  
          <Compensate.Target>  
            <InArgument  
               x:TypeArguments="CompensationToken">  
              <VariableValue  
                 x:TypeArguments="CompensationToken"  
                 Variable="{x:Reference __ReferenceID0}">  
                <VariableValue.Result>  
                  <OutArgument  
                     x:TypeArguments="CompensationToken" />  
                </VariableValue.Result>  
              </VariableValue>  
            </InArgument>  
          </Compensate.Target>  
        </Compensate>  
      </ActivityAction>  
    </Catch>  
  </TryCatch.Catches>  
</TryCatch>  
```  
  
 Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.  
  
 **ReserveFlight: Ticket wird reserviert.**  
**Simulatederrorcondition: Auslösen einer ApplicationException.** 
 **Cancelflight: Ticket wird abgebrochen.** 
 Der **Workflow wurde erfolgreich mit dem Status "geschlossen" abgeschlossen.**

### <a name="confirming-compensation"></a>Bestätigen einer Kompensation  

 Standardmäßig können kompensierbare Aktivitäten jederzeit kompensiert werden, nachdem sie abgeschlossen wurden. Für einige Szenarien eignet sich diese Vorgehensweise möglicherweise nicht. Im vorherigen Beispiel bestand die Kompensation bei der Reservierung des Tickets darin, den Reservierungsvorgang abzubrechen. Nachdem der Flug jedoch stattgefunden hat, ist dieser Kompensationsschritt nicht mehr gültig. Bei der Bestätigung der kompensierbaren Aktivität wird die Aktivität aufgerufen, die von <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> angegeben wird. Eine Verwendungsmöglichkeit dafür besteht darin, alle Ressourcen freizugeben, die für die Durchführung der Kompensation erforderlich sind. Nachdem eine kompensierbare Aktivität bestätigt wurde, kann sie nicht mehr kompensiert werden. Falls dies dennoch versucht wird, wird eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst. Wenn ein Workflow erfolgreich abgeschlossen wird, werden alle nicht bestätigten und nicht kompensierbaren Aktivitäten, die erfolgreich abgeschlossen wurden, in umgekehrter Reihenfolge Ihres Abschlusses bestätigt. In diesem Beispiel wird der Flug reserviert, gebucht und abgeschlossen, und dann wird die kompensierbare Aktivität bestätigt. Um ein <xref:System.Activities.Statements.CompensableActivity>-Objekt zu bestätigen, verwenden Sie die <xref:System.Activities.Statements.Confirm>-Aktivität, und geben Sie das <xref:System.Activities.Statements.CompensationToken>-Objekt des <xref:System.Activities.Statements.CompensableActivity>-Objekts an, das bestätigt werden soll.  
  
 [!code-csharp[CFX_CompensationExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 Dieses Beispiel ist der Workflow in XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <x:Reference>__ReferenceID0</x:Reference>  
  </Sequence.Variables>  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken">  
        <VariableReference  
           x:TypeArguments="CompensationToken">  
          <VariableReference.Result>  
            <OutArgument  
               x:TypeArguments="Location(CompensationToken)" />  
          </VariableReference.Result>  
          <VariableReference.Variable>  
            <Variable  
               x:TypeArguments="CompensationToken"  
               x:Name="__ReferenceID0"  
               Name="token1" />  
          </VariableReference.Variable>  
        </VariableReference>  
      </OutArgument>  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <CompensableActivity.ConfirmationHandler>  
      <c:ConfirmFlight />  
    </CompensableActivity.ConfirmationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
  <c:TakeFlight />  
  <Confirm>  
    <Confirm.Target>  
      <InArgument  
         x:TypeArguments="CompensationToken">  
        <VariableValue  
           x:TypeArguments="CompensationToken"  
           Variable="{x:Reference __ReferenceID0}">  
          <VariableValue.Result>  
            <OutArgument  
               x:TypeArguments="CompensationToken" />  
          </VariableValue.Result>  
        </VariableValue>  
      </InArgument>  
    </Confirm.Target>  
  </Confirm>  
</Sequence>  
```  
  
Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.  
  
**ReserveFlight: Ticket wird reserviert.**  
**ManagerApproval: die Genehmigung des Managers wurde empfangen.** 
 **Purchaseflight: Ticket wird gekauft.** 
 **Takeflight: Flug ist abgeschlossen.** 
 **Confirmflight: Flug wurde durchgeführt, keine Kompensierung möglich.** 
 Der **Workflow wurde erfolgreich mit dem Status "geschlossen" abgeschlossen.**

## <a name="nesting-compensation-activities"></a>Schachteln von Kompensationsaktivitäten  

Ein <xref:System.Activities.Statements.CompensableActivity>-Objekt kann in den Abschnitt <xref:System.Activities.Statements.CompensableActivity.Body%2A> eines anderen <xref:System.Activities.Statements.CompensableActivity>-Objekts eingefügt werden. <xref:System.Activities.Statements.CompensableActivity> darf nicht in einen Handler einer anderen <xref:System.Activities.Statements.CompensableActivity> eingefügt werden. Eine übergeordnete <xref:System.Activities.Statements.CompensableActivity> muss dafür sorgen, dass im Falle eines Abbruchs, einer Bestätigung oder Kompensation alle untergeordneten kompensierbaren Aktivitäten, die erfolgreich abgeschlossen und noch nicht bestätigt oder kompensiert wurden, bestätigt oder kompensiert werden, bevor die übergeordnete Aktivität den Abbruch, die Bestätigung oder Kompensation abschließt. Wenn dies nicht explizit modelliert wird, kompensiert die übergeordnete <xref:System.Activities.Statements.CompensableActivity> implizit untergeordnete kompensierbare Aktivitäten, wenn sie das Abbruch- oder Kompensationssignal empfängt. Nachdem die übergeordnete Aktivität das Bestätigungssignal empfangen hat, bestätigt sie implizit untergeordnete kompensierbare Aktivitäten. Wenn die Logik zur Behandlung des Abbruchs, der Bestätigung oder Kompensation explizit im Handler der übergeordneten <xref:System.Activities.Statements.CompensableActivity> modelliert wird, wird jede untergeordnete Aktivität, die nicht explizit behandelt wird, implizit bestätigt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Activities.Statements.CompensableActivity>
- <xref:System.Activities.Statements.Compensate>
- <xref:System.Activities.Statements.Confirm>
- <xref:System.Activities.Statements.CompensationToken>
