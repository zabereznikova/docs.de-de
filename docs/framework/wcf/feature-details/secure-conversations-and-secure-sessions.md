---
title: Sichere Unterhaltungen und sichere Sitzungen.
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d519640c40daf248a01a19f0450f3aea8de6cc04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="secure-conversations-and-secure-sessions"></a>Sichere Unterhaltungen und sichere Sitzungen.
Eine Funktion von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist die Fähigkeit, sichere Sitzungen zwischen zwei Endpunkten aufzubauen, die sich gegenseitig authentifizieren und sich auf ein Verfahren zur Verschlüsselung und digitalen Signatur einigen. Der Dienstendpunkt könnte beispielsweise einen Clientendpunkt benötigen, um zur Authentifizierung ein Sicherheitstoken zu senden, das auf einem X.509-Zertifikat basiert. Sobald der Client authentifiziert ist, gibt der Dienstendpunkt ein Sicherheitskontexttoken (SCT) an den Client zurück, das dann verwendet wird, um alle folgenden Nachrichten innerhalb der Sitzung zu sichern. Durch das Einrichten dieser sicheren Sitzung kann der Nachrichtensatz, der zwischen den beiden Endpunkten ausgetauscht wird, effizienter werden, da SCT über einen symmetrischen Schlüssel verfügt. In Bezug auf das Generieren einer digitalen Signatur oder Verschlüsseln eines Datensatzes erfordern asymmetrische Schlüssel, auf denen X.509-Zertifikate basieren, bedeutend mehr Rechenleistung als symmetrische Schlüssel.  
  
 Die bootstrap-Richtlinie (im Abschnitt 6.2.7 definiert die [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) die Nachricht Sicherheit Assertionen verwendet, um den Kanal sichern und Authentifizieren des Clients vor der RST/SCT und RSTR/SCT-Austausch enthält. Bestimmte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Standardbindungen verfügen über eine `Security.Message.EstablishSecurityContext`-Eigenschaft, welche steuert, ob eine sichere Konversation verwendet wird. Bei Verwendung von benutzerdefinierten Bindungen sind Bootstrapper durch Schachteln Sicherheitsbindungselemente entweder durch [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in der Konfigurationsdatei oder durch Aufrufen von <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> im Code.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Sitzungen, finden Sie unter [mit Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
