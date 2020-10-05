---
title: 'Vorgehensweise: Protokollinformationen über Dienste'
description: In diesem Artikel erhalten Sie Informationen zum Protokollieren von Informationen zu Diensten. Legen Sie die AutoLog-Eigenschaft fest, wenn Sie möchten, dass Ihr Windows-Dienstprojekt mit dem Anwendungsereignisprotokoll interagiert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
ms.openlocfilehash: 0d6c245e3defb7d518093cca904572d3db00fcf8
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608555"
---
# <a name="how-to-log-information-about-services"></a>Vorgehensweise: Protokollinformationen über Dienste
Standardmäßig können alle Windows-Dienst-Projekte auf das Anwendungsereignisprotokoll zugreifen und Informationen sowie Ausnahmen in das Protokoll schreiben. Sie geben über die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft an, ob Sie diese Funktionalität in Ihrer Anwendung nutzen möchten. Standardmäßig ist die Protokollierung für jeden Dienst aktiviert, den Sie mit den Projektvorlagen für Windows-Dienste erstellen. Sie können eine statische Form der <xref:System.Diagnostics.EventLog> -Klasse verwenden, um Dienstinformationen in ein Protokoll zu schreiben, ohne dass Sie eine Instanz von einer <xref:System.Diagnostics.EventLog> -Komponente erstellen oder eine Quelle manuell registrieren müssen.  
  
 Das Installationsprogramm für Ihren Dienst registriert jeden Dienst in Ihrem Projekt automatisch als gültige Quelle von Ereignissen für das Anwendungsprotokoll auf dem Computer, auf dem der Dienst installiert ist, wenn die Protokollierung aktiviert ist. Der Dienst protokolliert jedes Mal Informationen, wenn er gestartet, beendet, angehalten, fortgesetzt, installiert oder deinstalliert wird. Der Dienst protokolliert auch alle auftretenden Fehler. Wird das Standardverhalten verwendet, müssen Sie keinen Code schreiben, damit Einträge in das Protokoll geschrieben werden. Dies wird vom Dienst automatisch erledigt.  
  
 Wenn Sie möchten, dass nicht in das Anwendungsprotokoll, sondern in ein anderes Ereignisprotokoll geschrieben werden soll, müssen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft auf `false`festlegen, im Code Ihres Diensts Ihr eigenes Ereignisprotokoll erstellen und den Dienst als eine gültige Quelle für Einträge für dieses Protokoll registrieren. Danach müssen Sie Code schreiben, mit dem jedes Mal dann Einträge im Protokoll festgehalten werden, wenn eine Aktion auftritt, an der Sie interessiert sind.  
  
> [!NOTE]
> Wenn Sie ein benutzerdefiniertes Ereignisprotokoll verwenden und Ihren Dienst so konfigurieren, dass er in dieses Protokoll schreibt, dürfen Sie nicht versuchen, auf das Ereignisprotokoll zuzugreifen, bevor die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> -Eigenschaft des Diensts im Code festgelegt wurde. Der Wert dieser Eigenschaft ist für das Ereignisprotokoll erforderlich, damit Ihr Dienst als gültige Quelle für Ereignisse registriert werden kann.  
  
### <a name="to-enable-default-event-logging-for-your-service"></a>So aktivieren Sie die Standardereignisprotokollierung für Ihren Dienst  
  
- Legen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft für Ihre Komponente auf `true`fest.  
  
    > [!NOTE]
    > Standardmäßig ist diese Eigenschaft auf `true`festgelegt. Sie müssen dies nur dann explizit festlegen, wenn Sie eine komplexere Verarbeitung erstellen, etwa Auswerten einer Bedingung und dann Festlegen der <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft anhand des Ergebnisses dieser Bedingung.  
  
### <a name="to-disable-event-logging-for-your-service"></a>So deaktivieren Sie die Ereignisprotokollierung für Ihren Dienst  
  
- Legen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft für Ihre Komponente auf `false`fest.  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a>So richten Sie die Protokollierung in eine benutzerdefinierte Protokolldatei ein  
  
1. Legen Sie die <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> -Eigenschaft auf `false`fest.  
  
    > [!NOTE]
    > Sie müssen <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> auf „false“ festlegen, damit ein benutzerdefiniertes Protokoll verwendet werden kann.  
  
2. Richten Sie in Ihrer Windows-Dienst-Anwendung eine Instanz einer <xref:System.Diagnostics.EventLog> -Komponente ein.  
  
3. Erstellen Sie ein benutzerdefiniertes Protokoll, indem Sie die <xref:System.Diagnostics.EventLog.CreateEventSource%2A> -Methode aufrufen sowie die Quellzeichenfolge und den Namen der Protokolldatei angeben, die erstellt werden soll.  
  
4. Legen Sie die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft für die <xref:System.Diagnostics.EventLog> -Komponenteninstanz auf die Quellzeichenfolge fest, die Sie in Schritt 3 erstellt haben.  
  
5. Schreiben Sie die Einträge, indem Sie auf die <xref:System.Diagnostics.EventLog.WriteEntry%2A> -Methode der <xref:System.Diagnostics.EventLog> -Komponenteninstanz zugreifen.  
  
     Im folgenden Code wird veranschaulicht, wie Sie Protokollierung in ein benutzerdefiniertes Protokoll einrichten.  
  
    > [!NOTE]
    > In diesem Codebeispiel wird eine Instanz einer <xref:System.Diagnostics.EventLog> -Komponente mit `eventLog1` benannt (`EventLog1` in Visual Basic). Wenn Sie in Schritt 2 eine Instanz mit einem anderen Namen erstellt haben, ändern Sie den Code entsprechend.  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](introduction-to-windows-service-applications.md)
