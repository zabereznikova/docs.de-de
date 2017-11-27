---
title: Debuggen von Windows-Authentifizierungsfehlern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
- WCF, Windows authentication
ms.assetid: 181be4bd-79b1-4a66-aee2-931887a6d7cc
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f24dd1d597345f1aa8658073eef730832379b78c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="debugging-windows-authentication-errors"></a>Debuggen von Windows-Authentifizierungsfehlern
Bei Verwendung der Windows-Authentifizierung als Sicherheitsmechanismus wickelt die Security Support Provider-Schnittstelle (SSPI) Sicherheitsprozesse ab. Wenn Sicherheitsfehler auf der SSPI-Schicht auftreten, werden sie von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] festgestellt. Dieses Thema enthält ein Framework und eine Reihe von Fragen zur Diagnose der Fehler.  
  
 Einen Überblick über das Kerberos-Protokoll finden Sie unter [Kerberos erläutert](http://go.microsoft.com/fwlink/?LinkID=86946)– bzw. für ein Überblick über die SSPI, finden Sie unter [SSPI](http://go.microsoft.com/fwlink/?LinkId=88941).  
  
 Für Windows-Authentifizierung [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in der Regel verwendet die *Negotiate* Security Support Provider (SSP), die gegenseitige Kerberos-Authentifizierung zwischen Client und Dienst durchführt. Wenn das Kerberos-Protokoll nicht verfügbar ist, greift [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standardmäßig auf NT-LAN-Manager (NTLM) zurück. Sie können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] jedoch so konfigurieren, dass nur das Kerberos-Protokoll verwendet wird (und dass eine Ausnahme ausgelöst wird, wenn Kerberos nicht verfügbar ist). Sie können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch so konfigurieren, dass eingeschränkte Formen des Kerberos-Protokolls verwendet werden.  
  
## <a name="debugging-methodology"></a>Debugmethodik  
 Die grundlegende Methode lautet wie folgt:  
  
1.  Bestimmen Sie, ob Sie die Windows-Authentifizierung verwenden. Wenn Sie ein anderes Schema verwenden, ist dieses Thema irrelevant.  
  
2.  Wenn Sie sicher sind, dass Sie die Windows-Authentifizierung verwenden, bestimmen Sie, ob Ihre [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Konfiguration Kerberos direkt oder "Negotiate" verwendet.  
  
3.  Nachdem Sie festgestellt haben, ob Ihre Konfiguration das Kerberos-Protokoll oder NTLM verwendet, können Sie Fehlermeldungen im richtigen Kontext verstehen.  
  
### <a name="availability-of-the-kerberos-protocol-and-ntlm"></a>Verfügbarkeit des Kerberos-Protokolls und von NTLM  
 Der Kerberos SSP erfordert einen Domänencontroller, der als Kerberos Key Distribution Center (KDC) fungiert. Das Kerberos-Protokoll ist nur verfügbar, wenn sowohl der Client als auch der Dienst Domänenidentitäten verwenden. In anderen Kontokombinationen wird NTLM verwendet, wie in der folgenden Tabelle zusammengefasst.  
  
 Die Tabellenheader zeigen mögliche vom Server verwendete Kontotypen. Die linke Spalte zeigt mögliche vom Client verwendete Kontotypen.  
  
||Lokaler Benutzer|Lokales System|Domänenbenutzer|Domänencomputer|  
|-|----------------|------------------|-----------------|--------------------|  
|Lokaler Benutzer|NTLM|NTLM|NTLM|NTLM|  
|Lokales System|Anonymous NTLM|Anonymous NTLM|Anonymous NTLM|Anonymous NTLM|  
|Domänenbenutzer|NTLM|NTLM|Kerberos|Kerberos|  
|Domänencomputer|NTLM|NTLM|Kerberos|Kerberos|  
  
 Zu den vier Kontotypen gehören im Einzelnen:  
  
-   Lokaler Benutzer: Nur Computerbenutzerprofil. Beispiel: `MachineName\Administrator` oder `MachineName\ProfileName`.  
  
-   Lokales System: Das integrierte Konto SYSTEM auf einem Computer, der nicht mit einer Domäne verknüpft ist.  
  
-   Domänenbenutzer: Ein Benutzerkonto auf einer Windows-Domäne. Beispiel: `DomainName\ProfileName`.  
  
-   Domänencomputer: Ein Prozess mit Computeridentität, der auf einem Computer ausgeführt wird, der mit einer Windows-Domäne verknüpft ist. Beispiel: `MachineName\Network Service`.  
  
> [!NOTE]
>  Die Dienstanmeldeinformationen werden aufgezeichnet, wenn die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Klasse aufgerufen wird. Die Clientanmeldeinformationen werden immer dann gelesen, wenn der Client eine Nachricht sendet.  
  
## <a name="common-windows-authentication-problems"></a>Allgemeine Windows-Authentifizierungsprobleme  
 In diesem Abschnitt werden einige allgemeine Windows-Authentifizierungsprobleme und mögliche Abhilfen erläutert.  
  
### <a name="kerberos-protocol"></a>Kerberos-Protokoll  
  
#### <a name="spnupn-problems-with-the-kerberos-protocol"></a>SPN-/UPN-Probleme mit dem Kerberos-Protokoll  
 Bei Verwendung der Windows-Authentifizierung und des Kerberos-Protokolls oder der Aushandlung durch SSPI muss die vom Clientendpunkt verwendete URL den vollqualifizierten Domänennamen des Diensthosts in der Dienst-URL enthalten. Dabei wird vorausgesetzt, dass das Konto, unter dem der Dienst ausgeführt wird, Zugriff auf den (Standard-) Dienstprinzipalnamen (SPN) Dienstschlüssel, die erstellt wird hat, wenn der Computer der Active Directory-Domäne, der am häufigsten hinzugefügt wurde durch Ausführen des Dienstes unter erfolgt die Netzwerkdienstkonto. Wenn der Dienst keinen Zugriff auf den SPN-Schlüssel des Computers hat, müssen Sie den korrekten SPN oder Benutzerprinzipalnamen (UPN) des Kontos, unter dem der Dienst ausgeführt wird, in der Endpunktidentität des Clients angeben. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit SPN- und UPN, finden Sie unter [-Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 Eine gängige Praxis für Lastenausgleichszenarien (beispielsweise bei Webfarmen und Webgärten) ist das Definieren eines eindeutigen Kontos für die einzelnen Anwendungen. Anschließend wird dem Konto ein SPN zugewiesen und sichergestellt, dass alle Dienste der Anwendung in diesem Konto ausgeführt werden.  
  
 Zum Erhalten eines SPN für das Konto des Diensts müssen Sie Active Directory-Domänenadministrator sein. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Kerberos – technische Ergänzungfür Windows](http://go.microsoft.com/fwlink/?LinkID=88330).  
  
#### <a name="kerberos-protocol-direct-requires-the-service-to-run-under-a-domain-machine-account"></a>Kerberos-Protokoll Direct erfordert, dass der Dienst unter einem Domänencomputerkonto ausgeführt wird  
 Dieser Fehler tritt auf, wenn die `ClientCredentialType`-Eigenschaft auf `Windows` und die <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A>-Eigenschaft auf `false` festgelegt ist, wie im folgenden Code dargestellt.  
  
 [!code-csharp[C_DebuggingWindowsAuth#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#1)]
 [!code-vb[C_DebuggingWindowsAuth#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#1)]  
  
 Zum Beheben des Fehlers führen Sie den Dienst mit einem Domänencomputerkonto, wie Netzwerkdienst, auf einem Computer aus, der mit einer Domäne verknüpft ist.  
  
### <a name="delegation-requires-credential-negotiation"></a>Delegierung erfordert eine Anmeldeinformationen-Aushandlung  
 Um das Kerberos-Authentifizierungsprotokoll mit Delegierung zu verwenden, müssen Sie das Kerberos-Protokoll mit Anmeldeinformationen-Aushandlung (mitunter als "bilaterales" oder "mehrstufiges" Kerberos bezeichnet) implementieren. Wenn Sie die Kerberos-Authentifizierung ohne Anmeldeinformationen-Aushandlung (mitunter als "One-Shot"-Kerberos bezeichnet) implementieren, wird eine Ausnahme ausgelöst.  
  
 Um Kerberos mit Anmeldeinformationen-Aushandlung zu implementieren, führen Sie die folgenden Schritte aus:  
  
1.  Implementieren Sie die Delegierung, indem Sie <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> auf <xref:System.Security.Principal.TokenImpersonationLevel.Delegation> festlegen.  
  
2.  SSPI-Aushandlung erforderlich:  
  
    1.  Wenn Sie Standardbindungen verwenden, legen Sie die `NegotiateServiceCredential`-Eigenschaft auf `true` fest.  
  
    2.  Bei Verwendung von benutzerdefinierten Bindungen legen Sie das `AuthenticationMode`-Attribut des `Security`-Elements auf `SspiNegotiated` fest.  
  
3.  Legen Sie fest, dass die SSPI-Aushandlung Kerberos verwenden muss, indem Sie die Verwendung von NTLM nicht zulasssen:  
  
    1.  Führen Sie dies mit der folgenden Anweisung in Code aus: `ChannelFactory.Credentials.Windows.AllowNtlm = false`  
  
    2.  Sie können diese Einstellung auch in der Konfigurationsdatei vornehmen, indem Sie das `allowNtlm`-Attribut auf `false` festlegen. Dieses Attribut ist Bestandteil der [ \<Windows >](../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md).  
  
### <a name="ntlm-protocol"></a>NTLM-Protokoll  
  
#### <a name="negotiate-ssp-falls-back-to-ntlm-but-ntlm-is-disabled"></a>SSP-Aushandlung greift auf NTLM zurück, NTLM ist jedoch deaktiviert  
 Die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A>-Eigenschaft ist auf `false` festgelegt, wodurch von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein Best-Effort-Versuch unternommen wird, um bei Verwendung von NTLM eine Ausnahme auszulösen. Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM-Anmeldeinformationen über die Verbindung gesendet werden.  
  
 Die folgenden Schritte zeigen, wie ein Zurückgreifen auf NTLM deaktiviert wird.  
  
 [!code-csharp[C_DebuggingWindowsAuth#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#4)]
 [!code-vb[C_DebuggingWindowsAuth#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#4)]  
  
#### <a name="ntlm-logon-fails"></a>Fehler bei der NTLM-Anmeldung  
 Die Clientanmeldeinformationen sind im Dienst nicht gültig. Überprüfen Sie, ob Benutzername und Kennwort richtig eingestellt sind und einem Konto entsprechen, das dem Computer, auf dem der Dienst ausgeführt wird, bekannt ist. NTLM verwendet die angegebenen Anmeldeinformationen, um sich am Computer des Diensts anzumelden. Während die Anmeldeinformationen auf dem Computer, auf dem der Client ausgeführt wird, gültig sein können, schlägt diese Anmeldung fehl, wenn die Anmeldeinformationen für den Computer des Diensts nicht gültig sind.  
  
#### <a name="anonymous-ntlm-logon-occurs-but-anonymous-logons-are-disabled-by-default"></a>Anonyme NTLM-Anmeldung wird ausgeführt, anonyme Anmeldungen sind jedoch standardmäßig deaktiviert  
 Beim Erstellen eines Clients wird die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>-Eigenschaft auf <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous> festgelegt, wie im folgenden Beispiel veranschaulicht. Standardmäßig lässt der Server allerdings keine anonymen Anmeldungen zu. Dies tritt auf, da der Standardwert der <xref:System.ServiceModel.Security.WindowsServiceCredential.AllowAnonymousLogons%2A>-Eigenschaft der <xref:System.ServiceModel.Security.WindowsServiceCredential>-Klasse `false` ist.  
  
 Der folgende Clientcode versucht, anonyme Anmeldungen zu aktivieren (beachten Sie, dass die Standardeigenschaft `Identification` ist).  
  
 [!code-csharp[C_DebuggingWindowsAuth#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#5)]
 [!code-vb[C_DebuggingWindowsAuth#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#5)]  
  
 Der folgende Dienstcode ändert die Standardeinstellung, um anonyme Anmeldungen durch den Server zu aktivieren.  
  
 [!code-csharp[C_DebuggingWindowsAuth#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#6)]
 [!code-vb[C_DebuggingWindowsAuth#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#6)]  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Identitätswechsel finden Sie unter [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
 Alternativ wird der Client als Windows-Dienst ausgeführt und verwendet das integrierte Konto-SYSTEM.  
  
### <a name="other-problems"></a>Andere Probleme  
  
#### <a name="client-credentials-are-not-set-correctly"></a>Clientanmeldeinformationen werden nicht ordnungsgemäß festgelegt.  
 Die Windows-Authentifizierung verwendet die <xref:System.ServiceModel.Security.WindowsClientCredential>-Instanz, die von der <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>-Klasse zurückgegeben wird, nicht <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>. Im Folgenden wird ein nicht korrektes Beispiel dargestellt.  
  
 [!code-csharp[C_DebuggingWindowsAuth#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#2)]
 [!code-vb[C_DebuggingWindowsAuth#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#2)]  
  
 Im Folgenden wird ein korrektes Beispiel dargestellt.  
  
 [!code-csharp[C_DebuggingWindowsAuth#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#3)]
 [!code-vb[C_DebuggingWindowsAuth#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#3)]  
  
#### <a name="sspi-is-not-available"></a>SSPI ist nicht verfügbar  
 Die folgenden Betriebssysteme unterstützen keine Windows-Authentifizierung bei Verwendung als Server: [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Media Center Edition und [!INCLUDE[wv](../../../../includes/wv-md.md)]Home Edition.  
  
#### <a name="developing-and-deploying-with-different-identities"></a>Entwickeln und Bereitstellen mit unterschiedlichen Identitäten  
 Wenn Sie Ihre Anwendung auf einem bestimmten Computer entwickeln, die Anwendung anschließend auf einem anderen Computer bereitstellen und dabei unterschiedliche Kontotypen für die Authentifizierung verwenden, kann es vorkommen, dass sich das Verhalten von Computer zu Computer unterscheidet. Ein Beispiel: Angenommen, Sie entwickeln Ihre Anwendung auf einem Computer unter Windows&#160;XP&#160;Pro und verwenden dabei den `SSPI Negotiated`-Authentifizierungsmodus. Wenn die Authentifizierung unter Verwendung eines lokalen Benutzerkontos erfolgt, wird das NTLM-Protokoll verwendet. Nachdem die Entwicklung der Anwendung abgeschlossen ist, stellen Sie den Dienst für einen Computer unter Windows Server&#160;2003 bereit, wo er im Rahmen eines Domänenkontos ausgeführt wird. Der Dienst kann nun nicht mehr vom Client authentifiziert werden, da nun Kerberos und ein Domänencontroller verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 [Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
