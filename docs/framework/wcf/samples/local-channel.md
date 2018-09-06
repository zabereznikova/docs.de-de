---
title: Lokaler Kanal
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 731fcfde52a6b1277551f7d70f795c721fc99dd8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787596"
---
# <a name="local-channel"></a>Lokaler Kanal
Lokale Kanal ist ein Windows Communication Foundation (WCF)-Transportkanal, der für die Kommunikation innerhalb derselben Anwendungsdomäne verwendet wird. Dies ist nützlich bei Szenarien, in denen der Client und der Dienst in der gleichen Anwendungsdomäne ausgeführt werden und der Mehraufwand eines normalen WCF-Kanalstapels (Serialisierung und Deserialisierung von Meldungen) vermieden werden muss.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Lokaler Kanal  
  
## <a name="discussion"></a>Diskussion  
 Das Beispiel umfasst zwei Projektdateien.  
  
-   **LocalChannel**: die programmgesteuerte Darstellung des lokalen Kanals in der aktuellen Anwendungsdomäne. In diesem Projekt fügt die sendende Komponente die Nachricht einer Warteschlange im Arbeitsspeicher hinzu. Die empfangende Komponente ruft die Nachricht aus der Warteschlange ab, um sie zu empfangen.  
  
-   **ClientAndService**: dieses Projekt hostet einen Dienst in einer Konsolenanwendung und führt dann einen Client, um den Dienst von innerhalb der gleichen Anwendungsdomäne aufzurufen.  
  
 Aufgrund des Entwurfs des lokalen Kanals werden Kanalstapel und Serialisierungsvorgang ausgelassen, um die Geschwindigkeit zu erhöhen. Der lokale Transportkanal wird mit einer Warteschlange implementiert, mit der Dienstaufrufe vom Client zum Dienst transportiert und der Wert zum Client zurückgesendet wird. Im Beispiel werden die Objekte kopiert, statt Parameter und Rückgabewerte zu serialisieren.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Erstellen Sie die Projektmappe LocalChannel, und führen Sie sie aus.  
  
2.  Der Diensthost wird gestartet, und der Client ruft den Dienst mithilfe des lokalen Kanals auf. Ein Konsolenfenster mit den Ergebnissen des Dienstaufrufs wird angezeigt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
