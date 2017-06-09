---
title: "Sicherheits&#252;berlegungen f&#252;r Sicherheitssitzungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Sicherheits&#252;berlegungen f&#252;r Sicherheitssitzungen
Berücksichtigen Sie die folgenden Punkte, die sich bei der Implementierung von Sicherheitssitzungen auf die Sicherheit auswirken.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Sicherheitsüberlegungen finden Sie unter [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) und [Best Practices für Sicherheit](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## Sicherheitssitzungen und Metadaten  
 Wenn eine sichere Sitzung eingerichtet und die <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A>\-Eigenschaft auf `false` festgelegt ist, sendet [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] eine `mssp:MustNotSendCancel`\-Assertion als Bestandteil der Metadaten im WSDL\-Dokument \(Web Services Description Language\) für den Dienstendpunkt.Die `mssp:MustNotSendCancel`\-Assertion informiert Clients, dass der Dienst nicht auf Anforderungen zum Abbrechen der sicheren Sitzung reagiert.Wenn die <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A>\-Eigenschaft auf `true` gesetzt ist, gibt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine `mssp:MustNotSendCancel`\-Assertion im WSDL\-Dokument aus.Clients sollen eine Abbruchanforderung an den Dienst senden, wenn sie die sichere Sitzung nicht mehr benötigen.Wenn ein Client mit [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generiert wird, reagiert der Clientcode entsprechend auf die An\- oder Abwesenheit der `mssp:MustNotSendCancel`\-Assertion.  
  
## Sichere Unterhaltungen und benutzerdefinierte Token  
 Beim Mischen benutzerdefinierter Token und abgeleiteter Schlüssel ergeben sich aufgrund der Art der Definition in der WS\-SecureConversation\-Spezifikation einige Probleme.Laut Spezifikation ist `wsse:SecurityTokenReference` ein optionales Element, das auf das abgeleitete Token `/wsc:DerivedKeyToken/wsse:SecurityTokenReference` verweist. Dieses optionale Element wird verwendet, um Sicherheitskontexttoken, Sicherheitstoken oder freigegebenen Schlüssel\/geheime Schlüssel für die Ableitung anzugeben.Wird das Element nicht angegeben, wird davon ausgegangen, dass der Empfänger den freigegebenen Schlüssel dem Nachrichtenkontext entnehmen kann.Wenn der Kontext nicht bestimmt werden kann, sollte ein Fehler \(beispielsweise `wsc:UnknownDerivationSource`\) ausgelöst werden."  
  
 Das bedeutet, dass zum Ableiten eines benutzerdefinierten Tokens dessen Klauseltyp in ein `SecurityTokenReference`\-Element eingeschlossen werden muss.Zwar steht eine Option zum Deaktivieren der Ableitung zur Verfügung, standardmäßig werden Schlüssel jedoch abgeleitet.Wird der Schlüssel nicht eingeschlossen, ist zwar die Serialisierung des abgeleiteten Schlüsseltokens erfolgreich, bei der Deserialisierung wird jedoch eine Ausnahme ausgelöst.  
  
## Siehe auch  
 [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)   
 [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Best Practices für Sicherheit](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)