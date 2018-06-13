---
title: Sichere Unterhaltungen und sichere Sitzungen.
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c87f53bcaa167dd7b3b039c70129efca43742c1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497606"
---
# <a name="secure-conversations-and-secure-sessions"></a>Sichere Unterhaltungen und sichere Sitzungen.
Eine Funktion von Windows Communication Foundation (WCF) ist die Fähigkeit, sichere Sitzungen zwischen zwei Endpunkten aufzubauen, die sich gegenseitig authentifizieren und sich auf ein Verfahren zur Verschlüsselung und digitalen Signatur einigen. Der Dienstendpunkt könnte beispielsweise einen Clientendpunkt benötigen, um zur Authentifizierung ein Sicherheitstoken zu senden, das auf einem X.509-Zertifikat basiert. Sobald der Client authentifiziert ist, gibt der Dienstendpunkt ein Sicherheitskontexttoken (SCT) an den Client zurück, das dann verwendet wird, um alle folgenden Nachrichten innerhalb der Sitzung zu sichern. Durch das Einrichten dieser sicheren Sitzung kann der Nachrichtensatz, der zwischen den beiden Endpunkten ausgetauscht wird, effizienter werden, da SCT über einen symmetrischen Schlüssel verfügt. In Bezug auf das Generieren einer digitalen Signatur oder Verschlüsseln eines Datensatzes erfordern asymmetrische Schlüssel, auf denen X.509-Zertifikate basieren, bedeutend mehr Rechenleistung als symmetrische Schlüssel.  
  
 Die bootstrap-Richtlinie (im Abschnitt 6.2.7 definiert die [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) die Nachricht Sicherheit Assertionen verwendet, um den Kanal sichern und Authentifizieren des Clients vor der RST/SCT und RSTR/SCT-Austausch enthält. Bestimmte WCF--standardbindungen verfügen über eine `Security.Message.EstablishSecurityContext` Eigenschaft welche steuert, ob eine Konversation sichere verwendet wird. Bei Verwendung von benutzerdefinierten Bindungen sind Bootstrapper durch Schachteln Sicherheitsbindungselemente entweder durch [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in der Konfigurationsdatei oder durch Aufrufen von <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> im Code.  
  
 Weitere Informationen zu Sitzungen finden Sie unter [mit Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
