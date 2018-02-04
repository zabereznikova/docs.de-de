---
title: "Absolute Verzögerung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b483139a-39bb-4560-8003-8969a8fc2cd1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 60e3b65851dba68b4d01d6e4195b5faf99b583de
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="absolute-delay"></a>Absolute Verzögerung
Das Hauptszenario für dieses Beispiel ist die Verzögerung eines Vorgangs in einer Workflowanwendung mithilfe von permanenten Zeitgebern bis zu einem angegebenen Zeitpunkt (<xref:System.DateTime>). Dies unterscheidet sich von der Verwendung der integrierten <xref:System.Activities.Statements.Delay>-Aktivität, da ein Vorgang hierdurch nur für eine bestimmte Zeitspanne (<xref:System.TimeSpan>) bzw. eine Anzahl von Minuten/Sekunden verzögert werden kann.  
  
 In der Praxis kann diese Unterscheidung beispielsweise in den folgenden Fällen relevant sein:  
  
1.  Sie möchten das Senden einer E-Mail um 30 Sekunden verzögern, um sicherzustellen, dass Sie keine Fehler gemacht haben.  
  
2.  Sie machen Überstunden und möchten das Senden der E-Mails bis zu Beginn der normalen Geschäftszeit (z. B. 8:00) verzögern.  
  
## <a name="demonstrates"></a>Veranschaulicht  
  
1.  <xref:System.Activities.Statements.DurableTimerExtension> zum Implementieren einer absoluten Verzögerung  
  
2.  Einrichten von Persistenz mit <xref:System.Activities.WorkflowApplication> für permanente Zeitgeber  
  
3.  Verwenden von <xref:System.Activities.NativeActivity%601> zum Einsetzen von Erweiterungspunkten  
  
4.  Verwenden von <xref:System.Activities.CodeActivity%601> in der SendEmail-Aktivität  
  
5.  <xref:System.Activities.Statements.Delay>  
  
6.  Nur-XAML-Workflow  
  
 In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die einen <xref:System.DateTime> und permanente Zeitgeber zum Erfassen der Verzögerungsdauer beinhaltet. Wenn Sie permanente Zeitgeber verwenden, müssen Sie mithilfe von <xref:System.Activities.NativeActivity> ein Lesezeichen erstellen, da Sie dieses Lesezeichen bei der Zeitgebererweiterung registrieren müssen. In diesem Beispiel wird die `OnTimerExpired`-Methode aufgerufen, wenn der permanente Zeitgeber abläuft. Stellen Sie sicher, dass Sie die Zeitgebererweiterung dem <xref:System.Activities.NativeActivity%601.CacheMetadata%2A>-Ereignis hinzufügen, um sicherzustellen, dass diese Informationen der Laufzeit bereitgestellt werden. Das einzige andere Implementierungsdetail ist, dass Sie eine Logik für die Konvertierung von <xref:System.DateTime> in <xref:System.TimeSpan> implementieren müssen, da permanente Zeitgeber nur einen <xref:System.DateTime> umfassen. Beachten Sie, dass hierdurch ein kleiner Genauigkeitsfehler entsteht.  
  
> [!NOTE]
>  Durch das Konvertieren von <xref:System.DateTime> in <xref:System.TimeSpan> wird ein kleiner Genauigkeitsverlust verursacht.  
  
 In diesem Beispiel wird auch veranschaulicht, wie die Persistenz für <xref:System.Activities.WorkflowApplication> aktiviert wird. Für dieses spezielle Beispiel werden permanente Zeitgeber verwendet. Die Workflowdaten werden während der Leerlaufzeit in die Persistenzdatenbank entladen, während auf das Ablaufen des Zeitgebers gewartet wird. Diese Implementierung kann auch für andere Persistenzaktionen verwendet werden. In diesem Beispiel wird veranschaulicht, wie die Persistenzverbindungszeichenfolge mit SQL Server eingerichtet und der Instanzspeicher erstellt wird, um die Daten für Workflowinstanzen beizubehalten. Mit einer bereitgestellten Logik wird festlegt, wie der Workflow fortgesetzt wird, sobald ein Ereignis ausgelöst wird, das die Workflowinstanz ausführbar macht.  
  
 Während Sie in diesem Beispiel durchlaufen, sehen Sie sich, dass die Zeit, in der die integrierte Verzögerung beginnt und abgeschlossen ist, die wiederum, verursacht eine e-Mail-Nachricht gesendet werden. Ab diesem Punkt wird die AbsoluteDelay-Aktivität bis zum angegebenen Zeitpunkt (<xref:System.DateTime>) oder für 0 Sekunden angehalten, wenn der <xref:System.DateTime> abgelaufen ist. Nach dem Ablauf des Zeitgebers wird eine E-Mail gesendet. Dies veranschaulicht die zwei verschiedenen Anwendungsfälle der integrierten <xref:System.Activities.Statements.Delay>-Funktionen im Vergleich zum Verwenden einer AbsoluteDelay-Aktivität.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie SQL Server Express (oder höher) auf dem Computer installiert haben.  
  
2.  Führen Sie "setup.cmd" (aus "WF/Basic/Dienste/AbsoluteDelay/CS") in einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung aus, um die AbsoluteDelaySampleDB-Datenbank, das Persistenzschema die Persistenzlogik zu erstellen.  
  
3.  Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
4.  Geben Sie die Dauer in der Delay-Aktivität an.  
  
5.  Geben Sie die Ablaufzeit (ExpirationTime) in der AbsoluteDelay-Aktivität an.  
  
6.  Aktualisieren Sie die Felder "SendMailTo", "SendMailFrom", "SendMailSubject", "SendMailBody" und "SmtpHost" in der SendMail-Aktivität.  
  
    > [!NOTE]
    >  Wenn Sie keinen gültigen SMTP-Host eingeben, löst die Anwendung eine SMTP-Ausnahme aus.  
  
7.  Erstellen Sie die Projektmappe durch Auswahl **erstellen**, **Projektmappe**.  
  
8.  Führen Sie die Projektmappe durch Drücken von **F5**.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\AbsoluteDelay`
