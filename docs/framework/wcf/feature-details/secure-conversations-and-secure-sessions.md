---
title: Sichere Unterhaltungen und sichere Sitzungen.
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
ms.openlocfilehash: 6cbf877c80b7d10705868120c4ec4a7b40895114
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288501"
---
# <a name="secure-conversations-and-secure-sessions"></a>Sichere Unterhaltungen und sichere Sitzungen.

Eine Funktion von Windows Communication Foundation (WCF) ist die Möglichkeit, sichere Sitzungen zwischen zwei Endpunkten einzurichten, die einander authentifizieren und einem Verschlüsselungs-und digitalen Signatur Prozess zustimmen. Der Dienstendpunkt könnte beispielsweise einen Clientendpunkt benötigen, um zur Authentifizierung ein Sicherheitstoken zu senden, das auf einem X.509-Zertifikat basiert. Sobald der Client authentifiziert ist, gibt der Dienstendpunkt ein Sicherheitskontexttoken (SCT) an den Client zurück, das dann verwendet wird, um alle folgenden Nachrichten innerhalb der Sitzung zu sichern. Durch das Einrichten dieser sicheren Sitzung kann der Nachrichtensatz, der zwischen den beiden Endpunkten ausgetauscht wird, effizienter werden, da SCT über einen symmetrischen Schlüssel verfügt. In Bezug auf das Generieren einer digitalen Signatur oder Verschlüsseln eines Datensatzes erfordern asymmetrische Schlüssel, auf denen X.509-Zertifikate basieren, bedeutend mehr Rechenleistung als symmetrische Schlüssel.  
  
 Die Bootstrap-Richtlinie (die im Abschnitt 6.2.7 des [WS-SecurityPolicy](https://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/ws-securitypolicy-1.2-spec-os.html) -Standards definiert ist) enthält die Nachrichten Sicherheits Assertionen, die zum Sichern des Kanals und zum Authentifizieren des Clients vor RST/SCT und RSTR/SCT verwendet werden. Bestimmte WCF-Standard Bindungen verfügen über eine `Security.Message.EstablishSecurityContext` Eigenschaft, die steuert, ob eine sichere Konversation verwendet wird. Wenn Sie benutzerdefinierte Bindungen verwenden, wird der Bootstrap durch Schachteln der sicherheitsbindungs Elemente, entweder durch [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) in der Konfigurationsdatei oder durch Aufrufen von <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> im Code, angezeigt.  
  
 Weitere Informationen zu Sitzungen finden Sie unter [Verwenden von Sitzungen](../using-sessions.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Sitzungen, Instanziierung und Parallelität](sessions-instancing-and-concurrency.md)
- [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](how-to-create-a-service-that-requires-sessions.md)
