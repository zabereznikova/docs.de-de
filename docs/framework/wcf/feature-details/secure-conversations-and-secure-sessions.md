---
title: Sichere Unterhaltungen und sichere Sitzungen.
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d44a132f4bc4982ba0df437a56859de1a6fe441a
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332788"
---
# <a name="secure-conversations-and-secure-sessions"></a>Sichere Unterhaltungen und sichere Sitzungen.
Ein Feature von Windows Communication Foundation (WCF) ist die Möglichkeit, sichere Sitzungen zwischen zwei Endpunkten herzustellen, die sich gegenseitig authentifizieren und eine Verschlüsselung und digitalen einverstanden. Der Dienstendpunkt könnte beispielsweise einen Clientendpunkt benötigen, um zur Authentifizierung ein Sicherheitstoken zu senden, das auf einem X.509-Zertifikat basiert. Sobald der Client authentifiziert ist, gibt der Dienstendpunkt ein Sicherheitskontexttoken (SCT) an den Client zurück, das dann verwendet wird, um alle folgenden Nachrichten innerhalb der Sitzung zu sichern. Durch das Einrichten dieser sicheren Sitzung kann der Nachrichtensatz, der zwischen den beiden Endpunkten ausgetauscht wird, effizienter werden, da SCT über einen symmetrischen Schlüssel verfügt. In Bezug auf das Generieren einer digitalen Signatur oder Verschlüsseln eines Datensatzes erfordern asymmetrische Schlüssel, auf denen X.509-Zertifikate basieren, bedeutend mehr Rechenleistung als symmetrische Schlüssel.  
  
 Die bootstrap-Richtlinie (definiert in Abschnitt 6.2.7 des der [WS-SecurityPolicy](https://go.microsoft.com/fwlink/?LinkId=99817) standard) enthält die nachrichtensicherheitsassertionen verwendet, um die Sicherung des Kanals und Authentifizierung des Clients vor der RST/SCT- und RSTR/SCT-Austausch. Bestimmte standard-WCF-Bindungen haben eine `Security.Message.EstablishSecurityContext` Eigenschaft, die steuert, ob eine Konversation sichere verwendet wird. Bei Verwendung benutzerdefinierter Bindungen wird der Bootstrap-Stil durch Schachteln Sicherheitsbindungselemente, entweder über angegeben [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in der Konfigurationsdatei oder durch Aufrufen von <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> im Code.  
  
 Weitere Informationen zu Sitzungen finden Sie unter [mithilfe von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
