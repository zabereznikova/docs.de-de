---
title: "SuppressTransactionScope-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9fb46dfee70cdcf136578a32709f3ceddddbeb81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="suppress-transaction-scope"></a>SuppressTransactionScope-Aktivität
Anhand dieses Beispiels wird veranschaulicht, wie eine benutzerdefinierte `SuppressTransactionScope`-Aktivität erstellt wird, um die Ambient-Laufzeittransaktion zu unterdrücken, falls vorhanden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="sample-details"></a>Beispieldetails  
 Die benutzerdefinierte Aktivität ist nützlich, um den Fluss einer Transaktion an einen anderen Dienst zu verhindern, wenn der Transaktionsfluss in einer bestimmten Situation unerwünscht ist. Die Workflowlaufzeit verfügt über integrierte Unterstützung zur Unterdrückung der Ambient-Transaktion in der <xref:System.Activities.NativeActivity>-Klasse, zur Verwendung dieser Unterstützung muss jedoch eine benutzerdefinierte <xref:System.Activities.NativeActivity> erstellt werden wie in diesem Beispiel.  
  
 Das Szenario besteht aus drei Teilen. Zuerst erstellt ein <xref:System.Activities.Statements.TransactionScope> eine Laufzeittransaktion, die zur Ambient-Transaktion wird. Dies wird mit einer benutzerdefinierten Aktivität überprüft, die die lokalen und verteilten Bezeichner der Transaktion ausgibt. Die Transaktion wird dann an einen Remotedienst weitergegeben. Im zweiten Teil gibt der Workflow innerhalb eines `SuppressTransactionScope` die Transaktionsbezeichner erneut aus und die Transaktion erneut weiter. Die benutzerdefinierte Aktivität findet jedoch keine Ambient-Transaktion, und die an den Dienst weitergegebene Meldung enthält die Transaktion nicht. Daraufhin erstellt der Dienst eine Transaktion, sodass die auf dem Client und für den Dienst ausgegebenen verteilten Bezeichner nicht übereinstimmen. Im dritten und letzten Teil nach dem Beenden des `SuppressTransactionScope` wird die Laufzeittransaktion erneut zur Ambient-Transaktion, was durch eine weitere Meldung an den Dienst mit einem verteilten Bezeichner überprüft wird, der mit dem Bezeichner in der ersten Meldung übereinstimmt.  
  
 Die Aktivität selbst wird von <xref:System.Activities.NativeActivity> abgeleitet, da sie eine untergeordnete Aktivität planen und eine Ausführungseigenschaft hinzufügen muss. Der `SuppressTransactionScope` weist eine <xref:System.Activities.Variable> vom Typ <xref:System.Activities.RuntimeTransactionHandle> auf, die statt eines Instanzfelds vom Typ <xref:System.Activities.RuntimeTransactionHandle> verwendet werden muss, da das Handle initialisiert werden muss. Das `Variable<RuntimeTransactionHandle>` wird den Metadaten der Aktivität als Implementierungsvariable hinzugefügt, da es nur intern verwendet wird.  
  
 Bei Ausführung prüft die Aktivität zunächst, ob ein Textkörper angegeben wurde. Wenn dies der Fall ist, wird die `SuppressTransaction`-Eigenschaft für das <xref:System.Activities.RuntimeTransactionHandle> festgelegt. Nach Festlegen der Eigenschaft wird diese den Ausführungseigenschaften hinzugefügt und wird zur Ambient-Eigenschaft. Dies bedeutet, dass die Eigenschaft für jede dem `SuppressTransactionScope` untergeordnete Aktivität sichtbar ist, sodass die Unterdrückung der Laufzeittransaktion erzwungen wird und ein geschachtelter <xref:System.Activities.Statements.TransactionScope> eine Ausnahme auslöst. Nach Hinzufügen des Handles zu den Ausführungseigenschaften wird die Ausführung des Textkörpers geplant.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe "SuppressTransactionScope.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Um die Projektmappe zu erstellen, drücken Sie STRG + UMSCHALT + B, oder wählen Sie **Projektmappe** aus der **erstellen** Menü.  
  
3.  Sobald die Erstellung erfolgreich war, mit der rechten Maustaste in der Projektmappe, und wählen Sie **Startprojekte festlegen**. Wählen Sie im Dialogfeld **mehrere Startprojekte** und sicherzustellen, dass die Aktion für beide Projekte **starten**.  
  
4.  Drücken Sie F5, oder wählen Sie **Debuggen** aus der **Debuggen** Menü. Alternativ können Sie STRG + F5 oder wählen Sie **Starten ohne Debugging** aus der **Debuggen** -Menü, um ohne Debuggen auszuführen.  
  
    > [!NOTE]
    >  Der Server muss vor dem Starten des Clients ausgeführt werden. Die Ausgabe im Konsolenfenster, das den Dienst hostet, gibt an, wenn dieser gestartet wird.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`