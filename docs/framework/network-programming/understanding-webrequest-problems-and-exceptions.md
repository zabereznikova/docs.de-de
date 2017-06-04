---
title: "Grundlegendes zu WebRequest-Problemen und -Ausnahmen | Microsoft Docs"
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
ms.assetid: 74a361a5-e912-42d3-8f2e-8e9a96880a2b
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Grundlegendes zu WebRequest-Problemen und -Ausnahmen
<xref:System.Net.WebRequest> und die abgeleiteten Klassen \(<xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest> und <xref:System.Net.FileWebRequest>\) lösen Ausnahmen aus, um einer nicht ordnungsgemäßen Zustand zu signalisieren.  Manchmal ist die Lösung dieser Probleme nicht offensichtlich.  
  
## Projektmappen  
 Überprüfen Sie die <xref:System.Net.WebException.Status%2A>\-Eigenschaft <xref:System.Net.WebException>, um das Problem zu bestimmen.  In der folgenden Tabelle sind einige Statuswerte und mögliche Lösungen an.  
  
|Status|Details|Lösung|  
|------------|-------------|------------|  
|<xref:System.Net.WebExceptionStatus><br /><br /> \- oder \-<br /><br /> <xref:System.Net.WebExceptionStatus>|Es gibt ein Problem mit dem zugrunde liegenden Socket.  Die Verbindung gestellt möglicherweise zurück.|Stellen Sie erneut und senden Sie die Anforderung erneut.<br /><br /> Stellen Sie sicher, dass das neueste Service Pack installiert ist.<br /><br /> Erhöhen Sie den Wert der <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A?displayProperty=fullName>\-Eigenschaft.<br /><br /> Setzen Sie <xref:System.Net.HttpWebRequest.KeepAlive%2A?displayProperty=fullName> auf `false`.<br /><br /> Erhöhen Sie die maximale Anzahl von Verbindungen mit der <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>\-Eigenschaft.<br /><br /> Überprüfen Sie die Proxykonfiguration.<br /><br /> Wenn Sie SSL verwenden, stellen Sie sicher, dass der Serverprozess Berechtigung hat, auf den Zertifikatspeicher zuzugreifen.<br /><br /> Wenn Sie eine große Datenmenge übermittelte, legen Sie <xref:System.Net.HttpWebRequest.AllowWriteStreamBuffering%2A> zu `false` fest.|  
|<xref:System.Net.WebExceptionStatus>|Das Serverzertifikat konnte nicht überprüft werden.|Versuchen Sie, den URI mit Internet Explorer zu öffnen.  Lösen Sie alle Sicherheitswarnungen auf, die von IE angezeigt werden.  Wenn Sie die Sicherheitswarnung nicht beheben können, können Sie eine Zertifikatsrichtlinienklasse erstellen, die <xref:System.Net.ICertificatePolicy> implementiert, das `true` zurückgibt und an <xref:System.Net.ServicePointManager.CertificatePolicy%2A> führt.<br /><br /> Weitere Informationen finden Sie unter [http:\/\/support.microsoft.com\/?id\=823177](http://go.microsoft.com/fwlink/?LinkID=179653).<br /><br /> Stellen Sie sicher, dass das Zertifikat der Zertifizierungsstelle, die das Serverzertifikat signiert, zur vertrauenswürdigen Zertifizierungsstellenliste in Internet Explorer hinzugefügt wird.<br /><br /> Stellen Sie sicher, dass der Hostname im URL den allgemeinen Namen auf dem Serverzertifikat übereinstimmt.|  
|<xref:System.Net.WebExceptionStatus>|Fehler beim in der SSL\-Transaktion auf, oder es ist ein Zertifikatsproblem.|Mit .NET Framework 1,1 unterstützt nur SSL\-Version 3.0.  Wenn der Server nur TLS\-Version 1.0 oder 2,0 SSL\-Version verwendet, wird die Ausnahme ausgelöst.  Aktualisieren Sie auf .NET Framework Version 2.0 und zu True <xref:System.Net.ServicePointManager.SecurityProtocol%2A>, Server übereinstimmt.<br /><br /> Das Clientzertifikat wurde von einer Zertifizierungsstelle signiert der der Server nicht vertraut.  Installieren Sie das Zertifikat Ca auf dem Server.  Siehe [http:\/\/support.microsoft.com\/?id\=332077](http://go.microsoft.com/fwlink/?LinkID=179654).<br /><br /> Stellen Sie sicher, das neueste Service Pack installieren zu können.|  
|<xref:System.Net.WebExceptionStatus>|Die Verbindung konnte nicht hergestellt werden.|Eine Firewall oder ein Proxy blockiert die Verbindung.  Ändern Sie die Firewall oder den Proxy, um die Verbindung zu ermöglichen.<br /><br /> Legen Sie explizit <xref:System.Net.WebProxy> in der Clientanwendung fest, indem Sie den <xref:System.Net.WebProxy>\-Konstruktor aufrufen \(WebServiceProxyClass.Proxy \= neues, WebProxy \([http:\/\/server:80](http://server/) true\)\).<br /><br /> Führen Sie Filemon oder Regmon aus, um sicherzustellen, dass die Arbeitsprozessidentität die erforderlichen Berechtigungen verfügt, um auf WSPWSP.dll, HKLM\\System\\CurrentControlSet\\Services\\DnsCache oder HKLM\\System\\CurrentControlSet\\Services\\WinSock2 zuzugreifen.|  
|<xref:System.Net.WebExceptionStatus>|Der Domänennamen\-Dienst konnte den Hostnamen nicht auflösen.|Konfigurieren Sie den Proxy ordnungsgemäß.  Siehe [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> Stellen Sie sicher, dass keine installierte Antivirensoftware oder Firewall nicht die Verbindung blockiert.|  
|<xref:System.Net.WebExceptionStatus>|<xref:System.Net.WebRequest.Abort%2A> wurde aufgerufen oder ein Fehler aufgetreten.|Dieses Problem wird durch eine hoher Auslastung auf dem Client oder dem Server verursacht werden.  Verringern Sie die Last.<br /><br /> Vergrößern Sie die <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> Festlegen.<br /><br /> Siehe [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656), um Webdienstleistungseinstellungen zu ändern.|  
|<xref:System.Net.WebExceptionStatus>|Die Anwendung versucht, einen Socket zu schreiben, der bereits geschlossen wurde.|Der Client oder Server wird überladen.  Verringern Sie die Last.<br /><br /> Vergrößern Sie die <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> Festlegen.<br /><br /> Siehe [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656), um Webdienstleistungseinstellungen zu ändern.|  
|<xref:System.Net.WebExceptionStatus>|Die festgelegte Begrenzung \(<xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>\) auf der Nachrichtenlänge wurde überschritten.|Erhöhen Sie den Wert der <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>\-Eigenschaft.|  
|<xref:System.Net.WebExceptionStatus>|Der Domänennamen\-Dienst konnte den Proxyhostnamen nicht auflösen.|Konfigurieren Sie den Proxy ordnungsgemäß.  Siehe [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> Sie sollten <xref:System.Net.HttpWebRequest>, um keinen Proxy verwendet, indem Sie die <xref:System.Net.HttpWebRequest.Proxy%2A>\-Eigenschaft auf `null` festlegen.|  
|<xref:System.Net.WebExceptionStatus>|Die Antwort vom Server ist keine gültige HTTP\-Antwort.  Dieses Problem tritt auf, wenn .NET Framework erkennt, dass die Serverantwort nicht mit HTTP RFC 1.1 entspricht.  Dieses Problem tritt auf, wenn die Antwort falsche Header enthält, oder falscher Header delimiters.RFC 2616 HTTP 1.1 und das gültige Format für die Antwort vom Server definiert.  Weitere Informationen finden Sie unter [http:\/\/www.ietf.org](http://go.microsoft.com/fwlink/?LinkID=147388).|Rufen Sie eine Netzwerkablaufverfolgung der Transaktion ab und überprüfen Sie die Header in der Antwort.<br /><br /> Wenn die Anwendung die Serverantwort erfordert, ohne zu analysieren \(dies kann eine Sicherheitsrisiko sein\), legen Sie `useUnsafeHeaderParsing` zu `true` in der Konfigurationsdatei fest.  Siehe [\<httpWebRequest\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md).|  
  
## Siehe auch  
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.Dns>