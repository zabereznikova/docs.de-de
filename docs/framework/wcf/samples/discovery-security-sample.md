---
title: Beispiel für Ermittlungssicherheit
ms.date: 03/30/2017
ms.assetid: b8db01f4-b4a1-43fe-8e31-26d4e9304a65
ms.openlocfilehash: 0957e8ddaee99e60b205c92319dc2c61e2ab007a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292635"
---
# <a name="discovery-security-sample"></a>Beispiel für Ermittlungssicherheit

Die Discovery-Spezifikation erfordert nicht, dass Endpunkte, die am Suchvorgang beteiligt sind, sicher sein müssen. Die Erweiterung der Sicherheit von Suchmeldungen mindert das Risiko für verschiedene Angriffe (Meldungsänderung, Denial of Service, Wiederholung, Spoofing). In diesem Beispiel werden benutzerdefinierte Kanäle implementiert, die Meldungssignaturen mit dem kompakten Signaturformat berechnen und verifizieren. (Dies wird in Abschnitt 8.2 der WS-Discovery-Spezifikation beschrieben.) Das Beispiel unterstützt sowohl die [2005 Discovery-Spezifikation](http://specs.xmlsoap.org/ws/2005/04/discovery/ws-discovery.pdf) als auch die [1,1-Version](http://docs.oasis-open.org/ws-dd/discovery/1.1/cs-01/wsdd-discovery-1.1-spec-cs-01.pdf).  
  
 Der benutzerdefinierte Kanal wird an die oberste Stelle des vorhandenen Kanalstapels für Ermittlungs- und Ankündigungsendpunkte gesetzt. Auf diese Weise wird ein Signaturheader für jede gesendete Meldung übernommen. Die Signatur wird im Hinblick auf empfangene Meldungen überprüft. Wenn die Signatur nicht übereinstimmt oder die Meldungen nicht über eine Signatur verfügen, werden sie verworfen. Im Beispiel werden Zertifikate verwendet, um Meldungen zu signieren und zu überprüfen.  
  
## <a name="discussion"></a>Diskussion  

 WCF ist erweiterbar und ermöglicht den Benutzern die Möglichkeit, Kanäle wie gewünscht anzupassen. Im Beispiel wird ein sicheres Ermittlungsbindungselement implementiert, mit dem sichere Kanäle erstellt werden. Die sicheren Kanäle wenden Meldungssignaturen an und überprüfen diese. Sie werden an die oberste Stelle des aktuellen Stapels übernommen.  
  
 Mit dem sicheren Bindungselement werden sichere Kanalfactorys und Kanallistener erstellt.  
  
## <a name="secure-channel-factory"></a>Sichere Kanalfactory  

 Von der sicheren Kanalfactory werden Ausgabe- oder Duplexkanäle erstellt, mit denen Nachrichtenheadern eine kompakte Signatur hinzugefügt wird. Damit Meldungen möglichst klein bleiben, wird das kompakte Signaturformat verwendet. Im folgenden Beispiel wird die Struktur einer kompakten Signatur dargestellt.  
  
```xml  
<d:Security ... >
  [<d:Sig Scheme="xs:anyURI"
         [KeyId="xs:base64Binary"]?  
          Refs="..."  
         [PrefixList]="xs:NMTOKENS"
          Sig="xs:base64Binary"
          ... />]?  
  ...
</d:Security>  
```  
  
> [!NOTE]
> Die `PrefixList` wurde dem Protokoll der Discovery-Version 2008 hinzugefügt.  
  
 Im Beispiel werden die erweiterten Signaturelemente bestimmt, um die Signatur zu berechnen. Wie in der WS-Discovery-Spezifikation gefordert, wird eine XML-Signatur (`SignedInfo`) mit dem `ds`-Namespacepräfix erstellt. In der Signatur wird auf den Text und auf alle Header in Ermittlungs- und Adressierungsnamespaces verwiesen, damit diese nicht manipuliert werden können. Jedes referenzierte Element wird mit der exklusiven Kanonisierung ( <http://www.w3.org/2001/10/xml-exc-c14n#> ) transformiert, und dann wird ein SHA-1-Digestwert ( <http://www.w3.org/2000/09/xmldsig#sha1> ) berechnet. Basierend auf allen referenzierten Elementen und deren Digest-Werten wird der Signatur Wert mithilfe des RSA-Algorithmus ( <http://www.w3.org/2000/09/xmldsig#rsa-sha1> ) berechnet.  
  
 Die Meldungen werden mit einem vom Client angegebenen Zertifikat signiert. Der Speicherort, der Name und der Name des Zertifikat Antragstellers müssen angegeben werden, wenn das Bindungs Element erstellt wird. Die `KeyId` in der kompakten Signatur stellt den Schlüsselbezeichner des Signaturtokens dar und ist die Schlüsselkennung des Antragstellers (SKI) des Signaturtokens oder, wenn der SKI nicht vorhanden ist, ein SHA-1-Hash des öffentlichen Schlüssels des Signaturtokens.  
  
## <a name="secure-channel-listener"></a>Sicherer Kanallistener  

 Der sichere Kanallistener erstellt Eingabe- oder Duplexkanäle, die die kompakte Signatur in empfangenen Meldungen überprüfen. Um die Signatur zu überprüfen, wird die `KeyId` verwendet, die in der an die Meldung angefügten kompakten Signatur angegeben ist, um ein Zertifikat aus dem angegebenen Speicher auszuwählen. Wenn die Meldung über keine Signatur verfügt oder die Signaturüberprüfung nicht erfolgreich ist, werden die Meldungen verworfen. Im Beispiel wird zur Verwendung der sicheren Bindung eine Factory definiert, mit der benutzerdefinierte <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> und <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> mit dem zusätzlichen sicheren Ermittlungsbindungselement erstellt werden. Diese sicheren Endpunkte können in Discovery-Ankündigungslistenern und erkennbaren Diensten verwendet werden.  
  
## <a name="sample-details"></a>Beispieldetails  

 Das Beispiel enthält eine Bibliothek und 4 Konsolenanwendungen:
  
- **Discoverysecuritychannels**: eine Bibliothek, die die sichere Bindung verfügbar macht. Die Bibliothek berechnet und überprüft die kompakte Signatur für ausgehende/eingehende Meldungen.  
  
- **Dienst**: ein Dienst, der den ICalculatorService-Vertrag verfügbar macht, selbst gehostet. Der Dienst wird als erkennbar markiert. Der Benutzer gibt die Details des Zertifikats an, mit dem Meldungen signiert werden. Dazu werden Speicherort, Name und Antragsstellername oder andere eindeutige Bezeichner für das Zertifikat sowie der Speicher, in dem sich die Clientzertifikate befinden, angegeben. (Clientzertifikate sind Zertifikate, mit denen die Signatur auf eingehende Meldungen überprüft werden.) Auf Grundlage dieser Details wird ein UdpDiscoveryEndpoint mit zusätzlicher Sicherheit erstellt und verwendet.  
  
- **Client**: Diese Klasse versucht, einen ICalculatorService zu ermitteln und Methoden für den Dienst aufzurufen. Es wird ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> mit erweiterter Sicherheit erstellt, mit dem die Meldungen signiert und überprüft werden.  
  
- **Verküncementlistener**: ein selbst gehosteter Dienst, der Online-und Offline Ankündigungen abhört und den sicheren Ankündigungs Endpunkt verwendet.  
  
> [!NOTE]
> Wenn Setup.bat mehrmals ausgeführt wird, werden Sie vom Zertifikat-Manager dazu aufgefordert, ein Zertifikat auszuwählen, das hinzugefügt werden soll, da es doppelte Zertifikate gibt. In diesem Fall muss Setup.bat abgebrochen und Cleanup.bat aufgerufen werden, da die Duplikate bereits erstellt wurden. Sie werden außerdem von Cleanup.bat dazu aufgefordert, ein Zertifikat auszuwählen, das gelöscht werden soll. Wählen Sie ein Zertifikat aus der Liste aus, und führen Sie weiterhin Cleanup.bat aus, bis keine Zertifikate mehr verbleiben.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. Führen Sie das Setup.bat Skript aus einer Developer-Eingabeaufforderung für Visual Studio aus. Im diesem Beispiel werden Zertifikate verwendet, um Meldungen zu signieren und zu überprüfen. Das Skript erstellt die Zertifikate mit Makecert.exe und installiert sie dann mit Certmgr.exe. Das Skript muss mit Administratorberechtigungen ausgeführt werden.  
  
2. Um das Beispiel zu erstellen und auszuführen, öffnen Sie die Datei Security. sln in Visual Studio, und wählen Sie **alle neu erstellen** aus. Aktualisieren Sie die Projektmappeneigenschaften, um mehrere Projekte zu starten: Wählen Sie **Start** für alle Projekte außer discoverysecurechannels aus. Führen Sie die Projektmappe wie gewohnt aus.  
  
3. Nachdem Sie das Beispiel abgeschlossen haben, führen Sie das Skript Cleanup.bat aus. Damit werden alle für dieses Beispiel erstellten Zertifikate entfernt.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DiscoveryScenario`  
