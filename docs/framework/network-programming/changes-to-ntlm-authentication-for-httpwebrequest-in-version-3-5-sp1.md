---
title: "&#196;nderungen an der NTLM-Authentifizierung f&#252;r „HttpWebRequest“ in Version&#160;3.5 SP1 | Microsoft Docs"
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
ms.assetid: 8bf0b428-5a21-4299-8d6e-bf8251fd978a
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# &#196;nderungen an der NTLM-Authentifizierung f&#252;r „HttpWebRequest“ in Version&#160;3.5 SP1
Sicherheitsänderungen wurden in .NET Framework 3,5 SP1 und später in diesem Auswirkungen vorgenommen, wie die integrierte Windows\-Authentifizierung durch <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Security.NegotiateStream> und die verknüpften Klassen im System.Net\-Namespace behandelt wird.  Diese Änderungen können Anwendungen auswirken, die diese Klassen verwenden, um Webanforderungen zu stellen und Antworten zu empfangen, in denen die integrierte Windows\-Authentifizierung auf Grundlage NTLM verwendet wird.  Diese Änderung kann Webserver und Clientanwendungen auswirken, die so konfiguriert werden, um die Windows\-Authentifizierung zu verwenden.  
  
## Übersicht  
 Der Entwurf der integrierten Windows\-Authentifizierung darf, damit mehrere Anmeldeinformationen Antworten universell sind und sie bedeuten, können wiederverwendet werden oder weitergeleitet werden.  Wenn diese bestimmte Entwurfsfeature nicht erforderlich ist, sollten die Authentifizierungsprotokolle Informationen sowie Channelbesondereinformationen des Ziels tragen bestimmte.  Dienste können erweiterten Schutz dann bieten, um sicherzustellen, dass Anmeldeinformationen Antworten bestimmte Informationen des Diensts wie ein Dienstprinzipalname \(SPN\) enthalten.  Mit diesen Informationen in den Anmeldeinformationen Austausch, sind Dienste, vor böswilligen Verwendung von Anmeldeinformationen Antworten besser schützen, die möglicherweise nicht ordnungsgemäß abgerufen wurde.  
  
 Mehrere Komponenten in <xref:System.Net> und <xref:System.Net.Security>\-Namespaces führen integrierte Windows\-Authentifizierung im Namen eines aufrufende Anwendung aus.  In diesem Abschnitt werden Änderungen an System.Net\-Komponenten, um erweiterten Schutz in ihrem Verwendung von der integrierten Windows\-Authentifizierung hinzuzufügen.  
  
## Änderungen  
 Der NTLM\-Authentifizierungsprozess, der mit der integrierten Windows\-Authentifizierung verwendet wird, enthält eine Herausforderung, die durch den Zielcomputer und das zurückgeschickte auf den Clientcomputer ausgegeben wird.  Wenn ein Computer eine Herausforderung empfängt, die er sich generierte, schlägt die Authentifizierung aus, es sei denn, die Verbindung Schleifenbetrieb\-Verbindung ist eine IPv4\-Adresse \(127.0.0.1\).  
  
 Wenn es auf einen der internen auf einem Webserver zugreift, ist es häufig auf den Dienst, mit einer URL zuzugreifen, die in http:\/\/contoso\/service oder https:\/\/contoso\/service ähnelt.  Der Name "contoso" ist häufig nicht den Computernamen des Computers, auf dem der Dienst bereitgestellt wird.  <xref:System.Net> und verwandte die Namespaceunterstützung mit Active Directory, DNS, NetBIOSs, der Hostdatei des lokalen Computers \(in der Regel WINDOWS\\system32\\drivers\\etc\\hosts\), oder der lmhosts des lokalen Computers Dateien \(in der Regel WINDOWS\\system32\\drivers\\etc\\lmhosts\), um Namen den Adressen aufzulösen.  Der Name "contoso" aufgelöst wird, damit die Anforderungen, die auf "contoso" gesendet werden, zum entsprechenden Servercomputer gesendet werden.  
  
 Wenn es für große Bereitstellungen konfiguriert ist, ist auch üblich, dass ein einzelner Name des virtuellen Servers zur Bereitstellung mit den zugrunde liegenden Computernamen angegeben werden kann, die nie von Clientanwendungen und von den Endbenutzern verwendet werden.  Beispielsweise könnten Sie den Server www.contoso.com, jedoch auf einer Verwendung "contoso" des internen Netzwerks einfach auf.  Dieser Name wird den Host\-Header in der Clientwebanforderung aufgerufen.  Wie durch das HTTP\-Protokoll angegeben, gibt das Hostanforderungsheaderfeld den Internet\-Host und die Portnummer der Ressource an, die angefordert wird.  Diese Informationen werden aus der Vorlage URI abgerufen, die vom Benutzer oder die verweisende Ressource \(im Allgemeinen ein HTTP\-URL\) angegeben ist.  In .NET Framework, Version 4 können diese Informationen vom Client auch festgelegt werden, der die neue <xref:System.Net.HttpWebRequest.Host%2A>\-Eigenschaft verwendet.  
  
 Die <xref:System.Net.AuthenticationManager>\-Klasse steuert die verwalteten Authentifizierungskomponenten \("Module"\) die von abgeleiteten Klassen <xref:System.Net.WebRequest> und die <xref:System.Net.WebClient>\-Klasse verwendet werden.  Die <xref:System.Net.AuthenticationManager>\-Klasse stellt eine Eigenschaft, die ein <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName>\-Objekt verfügbar gemacht wird, indiziert durch URI\-Zeichenfolge, denn Anwendungen, eine während der Authentifizierung zu verwendende Zeichenfolge der benutzerdefinierten SPN anzugeben.  
  
 Version 3.5 SP1 gibt jetzt standardmäßig den in der Anforderungs\-URL verwendeten Hostnamen im SPN im NTLM \(NT LAN\-Manager\)\-Authentifizierungsaustausch an, wenn die <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A>\-Eigenschaft nicht festgelegt wird.  Der in der Anforderungs\-URL verwendete Hostname ist möglicherweise anders als der Hostheader, der in <xref:System.Net.HttpRequestHeader?displayProperty=fullName> in der Clientanforderung angegeben wurde.  Der in der Anforderungs\-URL verwendete Hostname unterscheidet sich möglicherweise vom tatsächlichen Hostnamen des Servers, vom Computernamen des Servers, von der IP\-Adresse des Computers oder von der Loopbackadresse.  In diesen Fällen schlägt die Authentifizierungsanforderung unter Windows fehl.  Um das Problem zu beheben, müssen wir Windows benachrichtigen dass der Hostname, der in der Anforderungs\-URL in der Clientanforderung verwendet wird \("contoso"\), tatsächlich ein alternativer Name für den lokalen Computer.  
  
 Es gibt mehrere Möglichkeiten, damit eine Serveranwendung um diese Änderung funktioniert.  Es empfiehlt sich, den Hostnamen zuzuordnen, der in der Anforderungs\-URL zur `BackConnectionHostNames` Schlüssel in der Registrierung auf dem Server verwendet wird.  Der `BackConnectionHostNames` Registrierungsschlüssel wird normalerweise verwendet, um einen Hostnamen zu einer Loopbackadresse zuzuordnen.  Die Schritte sind nachfolgend aufgeführt.  
  
 Um die Hostnamen anzugeben die zur Loopbackadresse zugeordnet werden und an Websites auf einem lokalen Computer herstellen können, führen Sie folgende Schritte aus:  
  
 1.  Klicken Sie auf Start und auf Ausführen, geben Sie „regedit“ ein, und klicken Sie anschließend auf OK.  
  
 2.  Suchen Sie im Registrierungs\-Editor und klicken Sie dann auf den folgenden Registrierungsschlüssel:  
  
 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\MSV1_0`  
  
 3.  Klicken Sie auf MSV1\_0 mit der rechten Maustaste, zeigen Sie auf Neu, und klicken Sie dann auf MULTI\-Zeichenfolge Wert.  
  
 4.  Geben Sie `BackConnectionHostNames` ein, und drücken Sie dann die EINGABETASTE.  
  
 5.  Klicken Sie auf `BackConnectionHostNames` mit der rechten Maustaste und dann ändern.  
  
 6.  In den Wertsdaten schachtelnde Sie, geben Sie den Hostnamen oder die Hostnamen für die Websites \(der Hostname verwendet in der Anforderungs\-URL\) und auf dem lokalen Computer sind ein, und klicken Sie dann auf OK.  
  
 7.  Lassen Sie den Registrierungs\-Editor und starten Sie den IISAdmin\-Dienst und das ausgeführte IISReset neu.  
  
 Eine weniger sichere Arbeit ist ungefähr, die Schleifenbetriebüberprüfung zu deaktivieren, wie in [http:\/\/support.microsoft.com\/kb\/896861](http://go.microsoft.com/fwlink/?LinkID=179657) beschrieben.  Dieses deaktiviert den Schutz gegen Reflektionsangriffe.  Daher ist es besser, den Satz von alternativen Namen auf lediglich die einzuschränken, die Sie den Computer erwarten, dass tatsächlich zu verwenden.  
  
## Siehe auch  
 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName>   
 <xref:System.Net.HttpRequestHeader?displayProperty=fullName>   
 <xref:System.Net.HttpWebRequest.Host%2A?displayProperty=fullName>