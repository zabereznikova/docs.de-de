---
title: Verhindern von Replay-Angriffen bei Hosten eines WCF-Diensts in einer Webfarm
ms.date: 03/30/2017
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
ms.openlocfilehash: e27a85d42268df107b26d3bd24af15a639bb1836
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072922"
---
# <a name="preventing-replay-attacks-when-a-wcf-service-is-hosted-in-a-web-farm"></a>Verhindern von Replay-Angriffen bei Hosten eines WCF-Diensts in einer Webfarm
Bei Verwendung von Nachrichtensicherheit verhindert WCF Replay-Angriffe, indem aus der eingehenden Nachricht eine NONCE erstellt und der `InMemoryNonceCache` daraufhin überprüft wird, ob die generierte NONCE vorhanden ist. Wenn dies der Fall ist, wird die Nachricht als Replay-Nachricht verworfen. Wenn ein WCF-Dienst in einer Webfarm gehostet wird, ist der Dienst für Replay-Angriffe anfällig, da der `InMemoryNonceCache` nicht für die Knoten in der Webfarm freigegeben ist.  Um die Bedrohung in diesem Szenario zu verringern, bietet WCF 4.5 einen Erweiterungspunkt, der Ihnen das Implementieren eines eigenen freigegebenen NONCE-Caches ermöglicht. Dies erfolgt durch das Ableiten einer Klasse von der abstrakten Klasse <xref:System.ServiceModel.Security.NonceCache>.  
  
## <a name="noncecache-implementation"></a>NonceCache-Implementierung  
 Zum Implementieren eines eigenen freigegebenen NONCE-Caches leiten Sie eine Klasse von <xref:System.ServiceModel.Security.NonceCache> ab, und überschreiben Sie die <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A>-Methode und die <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A>-Methode. <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> überprüft, ob die angegebene NONCE im Cache vorhanden ist. <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> versucht, dem Cache eine NONCE hinzuzufügen. Sobald die Klasse implementiert wurde, verknüpfen Sie sie, indem Sie eine Instanz instanziieren und sie <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> für die clientseitige Replay-Erkennung und <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> für die serverseitige Replay-Erkennung zuweisen. Es ist keine standardmäßige Konfigurationsunterstützung für diese Funktion verfügbar.  
  
## <a name="see-also"></a>Siehe auch

- [Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)
