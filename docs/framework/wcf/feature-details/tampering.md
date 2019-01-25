---
title: Verfälschungen
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: 86446778008782c733629ef94e6b192501bee2da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607185"
---
# <a name="tampering"></a>Verfälschungen
*Manipulationen* umfasst das Ändern einer Nachricht oder die Übermittlung einer Nachricht und Nutzung der geänderten Nachrichten für andere Zwecke als Ihren Zweck wurde.  
  
## <a name="do-not-disable-ws-addressing"></a>Deaktivieren Sie die WS-Adressierung nicht  
 Die WS-Adressierungsspezifikation bietet Adressheader für jede Nachricht, wodurch ein Nachrichtempfänger den Absender einer Nachricht bestätigen kann. Sie können diese Funktion deaktivieren, indem Sie die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> festlegen.  
  
 Wenn der Sicherheitsmodus auf "Nachricht" festgelegt ist und die WS-Adressierung deaktiviert, kann ein Angreifer eine Anforderung von einem Client nehmen und diese an einen anderen Dienst senden. Der zweite Dienst kann nicht erkennen, dass die Nachricht vom Original-Client kam. Der erste Dienst kann bei der Kommunikation mit dem zweiten Dienst vorgeben, ein Client zu sein.  
  
 Um dieses Problem zu lösen, sollten Sie nie die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> festlegen und die Nutzung von <xref:System.ServiceModel.Channels.MessageVersion> vermeiden, z. B. die statistische <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>-Eigenschaft, die die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> setzt.  
  
## <a name="see-also"></a>Siehe auch
- [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Offenlegung vertraulicher Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Erhöhen der Berechtigungen](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)
- [Denial-of-Service-Angriffe](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
- [Replayangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
