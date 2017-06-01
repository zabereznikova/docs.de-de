---
title: "Sichere Unterhaltungen und sichere Sitzungen. | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# Sichere Unterhaltungen und sichere Sitzungen.
Eine Funktion von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist die Fähigkeit, sichere Sitzungen zwischen zwei Endpunkten aufzubauen, die sich gegenseitig authentifizieren und sich auf ein Verfahren zur Verschlüsselung und digitalen Signatur einigen.Der Dienstendpunkt könnte beispielsweise einen Clientendpunkt benötigen, um zur Authentifizierung ein Sicherheitstoken zu senden, das auf einem X.509\-Zertifikat basiert.Sobald der Client authentifiziert ist, gibt der Dienstendpunkt ein Sicherheitskontexttoken \(SCT\) an den Client zurück, das dann verwendet wird, um alle folgenden Nachrichten innerhalb der Sitzung zu sichern.Durch das Einrichten dieser sicheren Sitzung kann der Nachrichtensatz, der zwischen den beiden Endpunkten ausgetauscht wird, effizienter werden, da SCT über einen symmetrischen Schlüssel verfügt.In Bezug auf das Generieren einer digitalen Signatur oder Verschlüsseln eines Datensatzes erfordern asymmetrische Schlüssel, auf denen X.509\-Zertifikate basieren, bedeutend mehr Rechenleistung als symmetrische Schlüssel.  
  
 Die Bootstrap\-Richtlinie \(die in Abschnitt 6.2.7 des [WS\-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817)\-Standards definiert ist\) enthält die Nachrichtensicherheitsassertionen, die vor dem RST\/SCT\- und RSTR\/SCT\-Austausch zur Sicherung des Kanals und Authentifizierung des Clients verwendet werden.Bestimmte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Standardbindungen verfügen über eine `Security.Message.EstablishSecurityContext`\-Eigenschaft, welche steuert, ob eine sichere Konversation verwendet wird.Bei Verwendung benutzerdefinierter Bindungen wird der Bootstrap durch die Schachtelung von Sicherheitsbindungselementen angegeben. Hierzu wird entweder in der Konfigurationsdatei [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) angegeben oder im Code <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> aufgerufen.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Sitzungen finden Sie unter [Verwenden von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
## Siehe auch  
 [Sitzungen, Instanziierung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)