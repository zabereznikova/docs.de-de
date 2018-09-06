---
title: Formularbereitstellung
ms.date: 03/30/2017
ms.assetid: fa6f84f9-2e07-4e3c-92d0-a245308b7dff
ms.openlocfilehash: 9115b9abfa7039bf409bb9bbce54e5012d05a074
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890827"
---
# <a name="form-post"></a>Formularbereitstellung
In diesem Beispiel wird veranschaulicht, wie das WCF-REST-Programmiermodell zur Unterstützung neuer Formate für eingehende Antworten erweitert wird. Das Beispiel umfasst auch die Implementierung eines Formatierungsprogramms, mit dem eine Anforderung von einer HTML-Formularbereitstellung in einen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ deserialisiert werden kann. Im Beispiel wird außerdem eine T4-Vorlage verwendet, um eine HTML-Seite zurückzugeben. Sie stellt das HTML-Formular bereit, das die Benutzer an den WCF REST-Dienst zurücksenden können.  
  
## <a name="demonstrates"></a>Veranschaulicht  
  
-   Erweitern der Unterstützung des Formats von eingehenden Anforderungen  
  
-   Integrieren von T4-Vorlagen  
  
## <a name="discussion"></a>Diskussion  
 Dieses Beispiel besteht aus zwei Projekten. Ein Projekt ist die HtmlFormProcessing-Bibliothek. Sie enthält ein benutzerdefiniertes Formatierungsprogramm für Anforderungen, mit dem HTML-Formularbereitstellungen zu [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen deserialisiert werden können. Das zweite Projekt ist eine Konsolenanwendung, mit der das Beispiel eines grundlegenden Ressourcendiensts dahingehend erweitert wird, dass ein benutzerdefiniertes Formatierungsprogramm für Anforderungen aus der HtmlFormProcessing-Bibliothek verwendet wird.  
  
 Das benutzerdefinierte Formatierungsprogramm kann HTML-Formularbereitstellungen (HtmlFormRequestDispatchFormatter) deserialisieren und akzeptiert beide [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen, die mithilfe des <xref:System.ServiceModel.Dispatcher.QueryStringConverter> und mit <xref:System.Runtime.Serialization.DataContractAttribute> markierten Typen von einer Zeichenfolge konvertiert werden können. Dieses Attribut verfügt nur über Member, die mit dem QueryStringConverter von einer Zeichenfolge konvertiert werden können.  
  
 Das HtmlFormProcessing-Bibliotheksprojekt enthält außerdem eine abstrakte Basisklasse, `RequestBodyDispatchFormatter`, mit der andere benutzerdefinierte Anforderungsformatierungsprogramme erstellt werden können. Die Ableitung vom `RequestBodyDispatchFormatter` ermöglicht es Entwicklern, sich auf die Deserialisierungslogik des Anforderungstexts zu konzentrieren. Auf diese Weise können die URI-Vorlagenparameter von der Basisklasse den Methodenparametern des Vorgangs zugeordnet werden. Im HtmlFormProcessing-Bibliothekprojekt befindet sich weiterhin die `HtmlFormProcessingBehavior`-Klasse, die veranschaulicht, wie vom <xref:System.ServiceModel.Description.WebHttpBehavior> abgeleitet wird, um das Standardformatierungsprogramm für Anforderungen durch ein benutzerdefiniertes Formatierungsprogramm für Anforderungen zu ersetzen.  
  
 Dieses Konsolenanwendungsprojekt erweitert die [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) Beispiel. Im Beispiel eines grundlegenden Ressourcendiensts wird veranschaulicht, wie eine Ressource in einer Weise verfügbar gemacht wird, die das WCF REST-Programmiermodell verwendet. Im Beispiel eines grundlegenden Ressourcendiensts wird eine Kundenauflistungsressource so verfügbar gemacht, dass Kunden in der Auflistung erstellt, abgerufen, aktualisiert und gelöscht werden können. Im Beispiel eines grundlegenden Ressourcendiensts werden nur die zwei systemintern unterstützten, eingehenden Anforderungsformate XML und JSON verwendet.  
  
 Die Konsolenanwendung in diesem Beispiel zur Formularbereitstellung verwendet das benutzerdefinierte Formatierungsprogramm in der HtmlFormProcessing-Bibliothek, mit dem Benutzer Kunden erstellen können, indem sie über einen Browser eine Anfrage von einer HTML-Formularbereitstellung senden. Damit wird auch ein Vorgang hinzugefügt, mit dem eine HTML-Seite zurückgegeben wird. Dazu gehört u. a., dass das Formular an den Dienst zurückgesendet wird. Diese HTML-Seite wird mit einer vorverarbeiteten T4-Vorlage generiert, die aus einer TT-Datei und einer automatisch generierten CS-Datei besteht. Die TT-Datei ermöglicht es Entwicklern, eine Antwort in ein Vorlagenformular zu schreiben, das Variablen und Steuerelementstrukturen enthält. Weitere Informationen zu T4 finden Sie unter [Generieren von Artefakten mithilfe von Textvorlagen](https://go.microsoft.com/fwlink/?LinkId=178139).  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das Beispiel zur Formularbereitstellung. Sie müssen [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator ausführen, damit das Beispiel erfolgreich ausgeführt werden kann. Zu diesem Zweck mit der rechten Maustaste die [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Symbol, und wählen "Als Administrator ausführen" aus dem Kontextmenü.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um das FormPost-Konsolenanwendungsprojekt auszuführen.  
  
3.  Im eingeblendeten Konsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt.  
  
4.  Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität in das Konsolenfenster, unabhängig davon, ob es sich dabei um das Hinzufügen, Aktualisieren oder Löschen eines Kunden oder das Abrufen einer Liste der aktuellen Kunden aus dem Dienst handelt.  
  
5.  Sie werden aufgefordert, zum URI des Kundenformulars zu wechseln. Öffnen Sie einen Browser, und wechseln Sie zum angegebenen URI. Geben Sie einen Namen und eine Adresse für den Kunden und klicken Sie auf die **senden** Schaltfläche.  
  
6.  Drücken Sie eine beliebige Taste, damit das Konsolenfenster das Beispiel weiterhin ausführt.  
  
7.  Beachten Sie, dass nach Abschluss des Beispiels der von Ihnen über den Browser erstellte Kunde in der finalen Kundenliste enthalten ist.  
  
8.  Drücken Sie eine beliebige Taste, um das Beispiel zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Web\FormPost`
