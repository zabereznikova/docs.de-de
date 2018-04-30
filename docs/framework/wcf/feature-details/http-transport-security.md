---
title: HTTP-Transportsicherheit
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3439262-c58e-4d30-9f2b-a160170582bb
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 2787c38603fd0f88878596a809d7e3c5cfdfb350
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="http-transport-security"></a>HTTP-Transportsicherheit
Bei der Verwendung von HTTP zum Transport wird die Sicherheit durch eine Secure Sockets Layer (SSL)-Implementierung bereitgestellt. SSL wird im Internet häufig verwendet, um einen Dienst gegenüber einem Client zu authentifizieren und anschließend Vertraulichkeit (Verschlüsselung) für den Kanal bereitzustellen. In diesem Thema wird die Funktionsweise von SSL und die Implementierung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erläutert.  
  
## <a name="basic-ssl"></a>Standard-SSL  
 Die Funktionsweise von SSL lässt sich am besten durch ein typisches Szenario erläutern, in diesem Fall die Website einer Bank. Die Website ermöglicht einem Kunden die Anmeldung mit Benutzernamen und Kennwort. Nach der Authentifizierung kann der Benutzer Transaktionen ausführen, z. B. den Kontostand anzeigen, Rechnungen begleichen und Geld auf ein anderes Konto überweisen.  
  
 Wenn ein Benutzer zuerst die Website besucht, startet der SSL-Mechanismus mehrere Aushandlungen, bezeichnet einen *Handshake*, mit dem Client des Benutzers (in diesem Fall Internet Explorer). SSL authentifiziert zuerst die Website der Bank für den Kunden. Dies ist ein wichtiger Schritt, da die Kunden zuerst wissen müssen, ob sie tatsächlich mit der Website kommunizieren und nicht auf einer vorgetäuschte Site ihren Benutzernamen und das Kennwort eingeben sollen. SSL führt diese Authentifizierung mit einem von einer vertrauenswürdigen Stelle, z. B. VeriSign, bereitgestellten SSL-Zertifikat durch. Die Logik ist wie folgt: VeriSign verbürgt sich für die Identität der Bank-Website. Da Internet Explorer VeriSign vertraut, ist die Site vertrauenswürdig. Wenn Sie Informationen zu VeriSign erhalten möchten, klicken Sie auf das VeriSign-Logo. Es wird eine Echtheitserklärung mit Ablaufdatum und Adressat der Ausstellung (die Bank-Website) angezeigt.  
  
 Zum Initiieren einer sicheren Sitzung sendet der Client das Äquivalent eines "Hallo" an den Server, zusammen mit einer Liste kryptografischer Algorithmen zum Signieren, Generieren von Hashs sowie zum Verschlüsseln und Entschlüsseln. Als Antwort sendet die Site eine Bestätigung und ihre Wahl einer der Algorithmensuites zurück. Während dieses ersten Handshakes senden und empfangen beide Seiten Nonces. Ein *Nonce* ist ein zufällig generierter Teil der Daten, die in Kombination mit dem öffentlichen Schlüssel des Standorts verwendet werden, zum Erstellen eines Hashs. Ein *Hash* ist eine neue Zahl, die von den beiden Zahlen mit einem Standardalgorithmus, z. B. SHA1 abgeleitet ist. (Der Client und die Site tauschen auch Nachrichten aus, um sich auf einen Hashalgorithmus zu einigen.) Der Hash ist eindeutig und wird nur für die Sitzung zwischen dem Client und der Website zum Verschlüsseln und Entschlüsseln von Nachrichten verwendet. Sowohl der Client als auch die Site verfügen über die ursprüngliche Nonce und den öffentlichen Schlüssel des Zertifikats, sodass beide Seiten den gleichen Hash generieren können. Deshalb prüft der Client den vom Dienst gesendeten Hash durch (a) Verwenden des vereinbarten Algorithmus zum Berechnen des Hashs auf Basis der Daten und durch (b) Vergleichen des Hashs mit dem vom Dienst gesendeten Hash. Stimmen die beiden überein, ist sichergestellt, dass der Hash nicht manipuliert wurde. Der Client kann dann diesen Hash als Schlüssel zum Verschlüsseln einer Nachricht verwenden, die noch einen weiteren neuen Hash enthält. Der Dienst kann die Nachricht mit dem Hash entschlüsseln und diesen vorletzten Hash wiederherstellen. Die gesammelten Informationen (Nonces, öffentlicher Schlüssel und andere Daten) sind jetzt beiden Seiten bekannt, und ein letzter Hash (oder Hauptschlüssel) kann erstellt werden. Dieser letzte Schlüssel wird verschlüsselt mit dem vorletzten Hash gesendet. Der Hauptschlüssel wird anschließend verwendet, um Nachrichten für das Zurücksetzen der Sitzung zu verschlüsseln und zu entschlüsseln. Da Client und Dienst den gleichen Schlüssel verwenden, dies wird auch bezeichnet eine *Sitzungsschlüssel*.  
  
 Der Sitzungsschlüssel wird auch als symmetrischer Schlüssel oder "gemeinsamer geheimer Schlüssel" gekennzeichnet. Ein symmetrischer Schlüssel ist wichtig, das er die von beiden Seiten für die Transaktion erforderliche Berechnung reduziert. Wenn jede Nachricht einen neuen Austausch von Nonces und Hashs erfordern würde, würde sich die Leistung verschlechtern. Daher ist das wichtigste Ziel von SSL die Verwendung eines symmetrischen Schlüssels, der die freie Übertragung von Nachrichten zwischen den beiden Seiten mit höherer Sicherheit und Effizienz ermöglicht.  
  
 Die vorangehende Beschreibung ist eine vereinfachte Version des Ablaufs, da die Protokolle je nach Website variieren können. Es ist auch möglich, dass sowohl der Client als auch die Site Nonces generieren, die während des Handshakes algorithmisch kombiniert werden, um mehr Komplexität und demzufolge Schutz für den Datenaustausch zu erreichen.  
  
### <a name="certificates-and-public-key-infrastructure"></a>Zertifikate und Public Key-Infrastruktur  
 Während des Handshakes sendet der Dienst auch sein SSL-Zertifikat an den Client. Das Zertifikat enthält Informationen wie Ablaufdatum, ausstellende Stelle und URI (Uniform Resource Identifier) der Website. Der Client vergleicht, ob der URI mit dem ursprünglich kontaktierten URI übereinstimmt, und überprüft auch das Datum und die ausstellende Stelle.  
  
 Jedes Zertifikat verfügt über zwei Schlüssel, einen privaten Schlüssel und ein öffentlicher Schlüssel ist und die beiden als bekannt sind ein *Austauschschlüsselpaar*. Kurz gesagt ist der private Schlüssel nur dem Besitzer des Zertifikats bekannt, während der öffentliche Schlüssel aus dem Zertifikat gelesen werden kann. Jeder der beiden Schlüssel kann zum Verschlüsseln oder Entschlüsseln eines Digests, Hashs oder anderen Schlüssels verwendet werden, jedoch nur als umgekehrte Vorgänge. Wenn z. B. der Client mit dem öffentlichen Schlüssel verschlüsselt, kann nur die Site die Nachricht mit dem privaten Schlüssel entschlüsseln. Analog kann der Client mit dem öffentlichen Schlüssel entschlüsseln, wenn die Site mit dem privaten Schlüssel verschlüsselt. Dies gibt dem Client die Gewissheit, dass die Nachrichten nur mit dem Besitzer des privaten Schlüssels ausgetauscht werden, da nur mit dem privaten Schlüssel verschlüsselte Nachrichten mit dem öffentlichen Schlüssel entschlüsselt werden können. Für die Site wird sichergestellt, dass sie Nachrichten mit einem Client austauscht, der mit dem öffentlichen Schlüssel verschlüsselt hat. Dieser Austausch ist jedoch nur für einen ersten Handshake sicher, daher wird mehr für das Erstellen des tatsächlichen symmetrischen Schlüssels getan. Alle Kommunikationen hängen trotzdem davon ab, dass der Dienst über ein gültiges SSL-Zertifikat verfügt.  
  
## <a name="implementing-ssl-with-wcf"></a>Implementieren von SSL mit WCF  
 HTTP-Transportsicherheit (oder SSL) wird [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] extern bereitgestellt. Sie können SSL auf zwei Wegen implementieren; der entscheidende Faktor ist, wie die Anwendung gehostet wird:  
  
-   Verwenden Sie die IIS-Infrastruktur zum Einrichten eines SSL-Dienstes, wenn Sie Internetinformationsdienste (IIS) als [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Host nutzen.  
  
-   Wenn Sie eine selbst gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung erstellen, können Sie mit dem Tool HttpCfg.exe ein SSL-Zertifikat an die Adresse binden.  
  
### <a name="using-iis-for-transport-security"></a>Verwenden von IIS für Transportsicherheit  
  
#### <a name="iis-70"></a>IIS 7.0  
 Zum Einrichten von [!INCLUDE[iisver](../../../../includes/iisver-md.md)] als sicheren Host (mit SSL), finden Sie unter [IIS 7.0 Beta: Konfigurieren von Secure Sockets Layer in IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88600).  
  
 So konfigurieren Sie Zertifikate für die Verwendung mit [!INCLUDE[iisver](../../../../includes/iisver-md.md)], finden Sie unter [IIS 7.0 Beta: Konfigurieren von Serverzertifikaten in IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=88595).  
  
#### <a name="iis-60"></a>IIS 6.0  
 Zum Einrichten von [!INCLUDE[iis601](../../../../includes/iis601-md.md)] als sicheren Host (mit SSL), finden Sie unter [Konfigurieren von Secure Sockets Layer](http://go.microsoft.com/fwlink/?LinkId=88601).  
  
 So konfigurieren Sie Zertifikate für die Verwendung mit [!INCLUDE[iis601](../../../../includes/iis601-md.md)], finden Sie unter [Certificates_IIS_SP1_Ops](http://go.microsoft.com/fwlink/?LinkId=88602).  
  
### <a name="using-httpcfg-for-ssl"></a>Verwenden von HttpCfg für SSL  
 Wenn Sie eine selbst gehostete erstellen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Anwendung, laden Sie das Tool HttpCfg.exe an die [Windows XP Service Pack 2-Supporttools Standort](http://go.microsoft.com/fwlink/?LinkId=29002).  
  
 Weitere Informationen zur Verwendung des Tools "HttpCfg.exe" Einrichten eines Ports mit einem x. 509-Zertifikat finden Sie unter [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
