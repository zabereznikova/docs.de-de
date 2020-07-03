---
title: Zertifikatauswahl und -überprüfung
description: Informieren Sie sich über verschiedene Möglichkeiten der System.Net-Klassen zum Auswählen und Überprüfen von Zertifikaten für SSL/TLS-Verbindungen.
ms.date: 03/30/2017
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
ms.openlocfilehash: 2dc63413f5c3a5fadd0d62ad61f0b887697c6a45
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502651"
---
# <a name="certificate-selection-and-validation"></a>Zertifikatauswahl und -überprüfung
Die <xref:System.Net>-Klassen unterstützen mehrere Möglichkeiten zur Auswahl und Überprüfung von <xref:System.Security.Cryptography.X509Certificates> für SSL-Verbindungen (Secure Socket Layer). Ein Client kann ein oder mehrere Zertifikate zur Authentifizierung gegenüber eines Servers wählen. Ein Server kann fordern, dass ein Clientzertifikat ein oder mehrere bestimmte Attribute für die Authentifizierung aufweist.  
  
## <a name="definition"></a>Definition  
 Ein Zertifikat ist ein ASCII-Datenstrom, der einen öffentlichen Schlüssel, Attribute (z.B. Versionsnummer, Seriennummer und Ablaufdatum) und eine digitale Signatur von einer Zertifizierungsstelle enthält. Zertifikate werden zum Herstellen einer verschlüsselten Verbindung oder zum Authentifizieren eines Clients mit einem Server verwendet.  
  
## <a name="client-certificate-selection-and-validation"></a>Zertifikatauswahl und -überprüfung  
 Ein Client kann ein oder mehrere Zertifikate für eine bestimmte SSL-Verbindung auswählen. Clientzertifikate können mit der SSL-Verbindung einem Webserver oder einen SMTP-Mailserver zugeordnet werden. Ein Client fügt Zertifikate zu einer Sammlung von <xref:System.Security.Cryptography.X509Certificates.X509Certificate>- oder <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Klassenobjekten hinzu. Nehmen wir E-Mails als Beispiel. Die Zertifikatauflistung ist eine Instanz von <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection>, die der <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A>-Eigenschaft der <xref:System.Net.Mail.SmtpClient>-Klasse zugeordnet ist. Die <xref:System.Net.HttpWebRequest>-Klasse verfügt über eine ähnliche <xref:System.Net.HttpWebRequest.ClientCertificates%2A>-Eigenschaft.  
  
 Der Hauptunterschied zwischen der <xref:System.Security.Cryptography.X509Certificates.X509Certificate>- und der <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Klasse ist, dass sich der private Schlüssel für die <xref:System.Security.Cryptography.X509Certificates.X509Certificate>-Klasse im Zertifikatspeicher befinden muss.  
  
 Auch wenn Zertifikate zu einer Auflistung hinzugefügt und einer bestimmten SSL-Verbindung zugeordnet werden, werden keine Zertifikate an den Server gesendet, außer der Server fordert dies an. Wenn mehrere Clientzertifikate für eine Verbindung festgelegt werden, wird das beste verwendet werden. Diese Entscheidung basiert auf einem Algorithmus, der die Übereinstimmung zwischen der durch den Server bereitgestellten Liste der Zertifikataussteller und den Ausstellernamen für Clientzertifikate berücksichtigt.  
  
 Die <xref:System.Net.Security.SslStream>-Klasse stellt noch mehr Kontrolle über den SSL-Handshake bereit. Ein Client kann einen Delegaten zum Auswählen des zu verwendenden Clientzertifikats angeben.  
  
 Ein Remoteserver kann überprüfen, ob ein Clientzertifikat gültig, aktuell und von der entsprechenden Zertifizierungsstelle unterzeichnet ist. Ein Delegat kann zu <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> hinzugefügt werden, um die Überprüfung des Zertifikats zu erzwingen.  
  
## <a name="client-certificate-selection"></a>Clientzertifikatauswahl  
 .NET Framework wählt das Clientzertifikat aus, das dem Server auf folgende Weise präsentiert wird:  
  
1. Wenn ein Clientzertifikat dem Server bereits gezeigt wurde, wird das Zertifikat beim ersten Mal zwischengespeichert und für nachfolgende Clientzertifikatanforderungen wiederverwendet.  
  
2. Wenn ein Delegat vorhanden ist, verwenden Sie immer das Ergebnis aus dem Delegaten als auszuwählendes Clientzertifikat. Versuchen Sie nach Möglichkeit ein zwischengespeichertes Zertifikat zu verwenden, aber verwenden Sie keine zwischengespeicherten anonymen Anmeldeinformationen, wenn der Delegat NULL zurückgegeben hat und die Zertifikatauflistung nicht leer ist.  
  
3. Ist dies die erste Abfrage für ein Clientzertifikat, listet das Framework die Zertifikate in <xref:System.Security.Cryptography.X509Certificates.X509Certificate>- oder <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Klassenobjekten auf, die der Verbindung zugeordnet sind. Sie suchen nach einer Übereinstimmung zwischen der vom Server bereitgestellten Liste der Zertifikataussteller und dem Ausstellernamen für Clientzertifikate. Das erste übereinstimmende Zertifikat wird an den Server gesendet. Wenn kein Zertifikat übereinstimmt oder die Zertifikatauflistung leer ist, wird eine anonyme Anmeldeinformation an den Server gesendet.  
  
## <a name="tools-for-certificate-configuration"></a>Tools für die Zertifikatkonfiguration  
 Eine Reihe von Tools stehen für die Zertifikatkonfiguration für Client und Server zur Verfügung.  
  
 Das *Winhttpcertcfg.exe*-Tool kann zur Konfiguration von Clientzertifikaten verwendet werden. Das *Winhttpcertcfg.exe*-Tool wird als eines der Tools im Windows Server 2003 Resource Kit bereitgestellt. Dieses Tool steht auch als Teil der Windows Server 2003 Ressource Kit-Tools unter [www.microsoft.com](https://www.microsoft.com) zum Download zur Verfügung.  
  
Das *HttpCfg.exe*-Tool kann verwendet werden, um Serverzertifikate für die <xref:System.Net.HttpListener>-Klasse zu konfigurieren. Das *HttpCfg.exe*-Tool dient als eines der Supporttools für Windows Server 2003 und Windows XP Service Pack 2. *HttpCfg.exe* und die anderen Supporttools werden standardmäßig unter Windows Server 2003 oder Windows XP installiert. Unter Windows Server 2003 werden die Supporttools separat vom folgenden Ordner und der Datei auf der Windows Server 2003-CD-ROM installiert:  
  
 \Support\Tools\Suptools.msi  
  
 Für die Verwendung mit Windows XP Service Pack 2 stehen Windows XP-Supporttools unter [www.microsoft.com](https://www.microsoft.com) zum Download zur Verfügung.  
  
 Der Quellcode für eine Version des *HttpCfg.exe*-Tools wird auch als ein Beispiel mit dem Windows Server SDK bereitgestellt. Der Quellcode des *HttpCfg.exe*-Beispiels wird standardmäßig mit den Netzwerkbeispielen als Teil der Windows SDK unter folgendem Ordner installiert:  
  
 *C:\Programme\Microsoft SDKs\Windows\v1.0\Samples\NetDS\http\serviceconfig*  
  
 Zusätzlich zu diesen Tools stellen die <xref:System.Security.Cryptography.X509Certificates.X509Certificate>- und <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Klassen Methoden zum Laden eines Zertifikats aus dem Dateisystem bereit.  
  
## <a name="see-also"></a>Siehe auch

- [Security in Network Programming (Sicherheit in der Netzwerkprogrammierung)](security-in-network-programming.md)
- [Netzwerkprogrammierung in .NET Framework](index.md)
