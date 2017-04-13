---
title: "Zertifikatauswahl und -&#252;berpr&#252;fung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Zertifikatauswahl und -&#252;berpr&#252;fung
Die <xref:System.Net>\-Klassen unterstützen einige Methoden, <xref:System.Security.Cryptography.X509Certificates> für Verbindungen von SSL \(Secure Sockets Layer\) auszuwählen und zu überprüfen.  Ein Client kann eine oder mehrere Zertifikate auswählen, um auf einem Server zu authentifizieren.  Ein Server kann erfordern, dass ein Clientzertifikat eine oder mehrere bestimmte Attribute für Authentifizierung haben.  
  
## Definition  
 Ein Zertifikat ist ein ASCII\-Bytestrom, der einen öffentlichen Schlüssel, Attribute \(wie Versionsnummer, Seriennummer und Ablaufdatum\) und einer digitalen Signatur von einer Zertifizierungsstelle enthält.  Zertifikate werden, um eine verschlüsselte Verbindung festzulegen verwendet oder einen Client an einem Server zu authentifizieren.  
  
## Client\-Zertifikats\-Auswahl und Validierung  
 Ein Client kann eine oder mehrere Zertifikate für eine Verbindung der spezifischen SSL auswählen.  Clientzertifikate können mit der SSL\-Verbindung auf einem Webserver oder einem SMTP\-Mailserver zugeordnet werden.  Ein Client fügt Zertifikate einer Auflistung <xref:System.Security.Cryptography.X509Certificates.X509Certificate> oder <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>\-Klassenobjekten hinzu.  Verwenden der E\-Mail als Beispiel, ist die Zertifikatsauflistung eine Instanz von <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection>\), das mit der <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A>\-Eigenschaft der <xref:System.Net.Mail.SmtpClient>\-Klasse zugeordnet ist.  Die <xref:System.Net.HttpWebRequest>\-Klasse hat eine ähnliche <xref:System.Net.HttpWebRequest.ClientCertificates%2A>\-Eigenschaft.  
  
 Der primäre Unterschied zwischen <xref:System.Security.Cryptography.X509Certificates.X509Certificate> und der <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>\-Klasse besteht darin, dass der private Schlüssel im Zertifikatspeicher für die <xref:System.Security.Cryptography.X509Certificates.X509Certificate>\-Klasse befinden muss.  
  
 Auch wenn Zertifikate zu einer Auflistung hinzugefügt und mit einer Verbindung der spezifischen SSL zugeordnet, werden keine Zertifikate an den Server gesendet, es sei denn, der Server diese anfordert.  Wenn mehrere Clientzertifikate auf eine Verbindung festgelegt werden, wird das beste von auf Grundlage eines Algorithmus, der die Übereinstimmung zwischen der Liste der Zertifikatsausstellern betrachtet, die vom Server bereitgestellt und dem Clientzertifikatsausstellernamen.  
  
 Die <xref:System.Net.Security.SslStream>\-Klasse stellt sogar Kontrolle über das SSL\-Handshake bereit.  Ein Client kann einen Delegaten angeben, um auszuwählen, der auf das Clientzertifikat verwenden.  
  
 Ein Remoteserver kann überprüfen, ob ein Clientzertifikat gültig aktuell ist, und durch die entsprechende Zertifizierungsstelle signiert.  Ein Delegat kann <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> hinzugefügt werden, um Zertifikatsvalidierung zu erzwingen.  
  
## Client\-Zertifikats\-Auswahl  
 . .NET Framework wählt das Clientzertifikat aus, um den Server in der folgenden Weise darzustellen:  
  
1.  Wenn ein Clientzertifikat zuvor dem Server erzeugt wurde, wird das Zertifikat zwischengespeichert, wenn es zuerst dargestellt wird und für folgende Clientzertifikatsanforderungen wiederverwendet.  
  
2.  Wenn ein Delegat vorhanden ist, verwenden Sie immer das Ergebnis vom Delegaten als das Clientzertifikat, um auszuwählen.  Versuchen Sie, ein zwischengespeichertes Zertifikat zu verwenden, wenn möglich, aber, verwenden Sie keine zwischengespeicherten anonyme Anmeldeinformationen, wenn der Delegat NULL zurückgegeben hat und die Zertifikatsauflistung nicht leer ist.  
  
3.  Wenn dies die erste Herausforderung für ein Clientzertifikat ist, sucht das Framework auflistet die Zertifikate in <xref:System.Security.Cryptography.X509Certificates.X509Certificate> oder die <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>\-Klassenobjekte, die der Verbindung zugeordnet und nach einer Übereinstimmung zwischen der Liste der Zertifikatsausstellern, die vom Server bereitgestellt und dem Clientzertifikatsausstellernamen.  Das erste Zertifikat, das entspricht, wird an den Server gesendet.  Wenn kein Zertifikat entspricht, oder die Zertifikatsauflistung leer ist, werden anonyme Anmeldeinformationen an den Server gesendet.  
  
## Tools für Zertifikats\-Konfiguration  
 Einige Tools sind für Client\- und Serverzertifikatskonfiguration verfügbar.  
  
 Das *Winhttpcertcfg.exe* Tool kann verwendet werden, um Clientzertifikate zu konfigurieren.  Das *Winhttpcertcfg.exe* Tool wird als eines der Tools mit dem Windows Server 2003\-Ressourcen\-Kit bereitgestellt.  Dieses Tool ist auch als Download als Teil der Windows Server 2003\-Ressourcen\-Kit\-Tools unter www.microsoft.com verfügbar.  
  
 *Das HttpCfg.exe* Tool kann verwendet werden, um Serverzertifikate für die <xref:System.Net.HttpListener>\-Klasse zu konfigurieren.  Das *HttpCfg.exe* Tool wird als eines der Stütztools für Windows Server 2003 und Windows XP Service Pack 2 bereitgestellt.  *HttpCfg.exe* und die anderen Stütztools werden standardmäßig entweder nicht unter Windows Server 2003 oder Windows XP installiert.  Unter Windows Server 2003.  die Stütztools werden separat aus dem folgenden Ordner und von der Datei auf dem Windows Server 2003\-CD\-ROM installiert:  
  
 \\Support\\Tools\\Suptools.msi  
  
 Für die Verwendung mit Windows XP Service Pack 2, sind die Windows XP\-Supporttools als Download von www.microsoft.com verfügbar.  
  
 Der Quellcode zu einer Version des Tools *HttpCfg.exe* wird auch als Beispiel mit dem Windows SDK Server bereitgestellt.  Der Quellcode für das *HttpCfg.exe* Beispiel wird standardmäßig mit den Netzwerkfunktionsbeispielen als Teil des Windows SDKs unter dem folgenden Ordner installiert:  
  
 *C:\\Programme\\Microsoft SDKs\\Windows\\v1.0\\Samples\\NetDS\\http\\serviceconfig*  
  
 Zusätzlich zu diesen Tools stellt die <xref:System.Security.Cryptography.X509Certificates.X509Certificate><xref:System.Security.Cryptography.X509Certificates.X509Certificate2>\-Klassen und Methoden für das Laden eines Zertifikats aus dem Dateisystem bereit.  
  
## Siehe auch  
 [Sicherheit in der Netzwerkprogrammierung](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)