---
title: 'Einblicke in den CustomPeerResolverService: Clientregistrierungen'
ms.date: 03/30/2017
ms.assetid: 40236953-a916-4236-84a6-928859e1331a
ms.openlocfilehash: ce694408edbb40309d1750be49b8414ebcbce3f7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596837"
---
# <a name="inside-the-custompeerresolverservice-client-registrations"></a>Einblicke in den CustomPeerResolverService: Clientregistrierungen
Jeder Knoten im Netz veröffentlicht seine Endpunktinformationen für den Resolverdienst durch die `Register`-Funktion. Der Resolverdienst speichert diese Informationen als Registrierungsdatensatz. Dieser Datensatz enthält einen eindeutigen Bezeichner (RegistrationID) sowie Endpunktinformationen (PeerNodeAddress) für den Knoten.  
  
## <a name="stale-records-and-expiration-time"></a>Veraltete Datensätze und Ablaufzeit  
 Idealerweise ruft ein Knoten beim Verlassen des Netzes die `Unregister`- Funktion auf, wodurch der Registrierungseintrag vom Resolverdienst entfernt wird. Manchmal werden Knoten jedoch geschlossen oder nicht verfügbar, bevor `Unregister` aufgerufen wurde. Dadurch bleibt ein veralteter Registrierungsdatensatz zurück.  
  
 Veraltete Datensätze im Resolverdienst können zu fehlerhaften Verbindungen führen. Erhält ein Knoten beim Versuch, eine Verbindung mit einem Netz herzustellen, veraltete Verbindungsinformationen vom Resolverdienst, dauert es ggf. länger, bis er eine erfolgreiche Verknüpfung zu dem Netz herstellen kann. Veraltete Datensätze belegen zudem Speicherplatz. Ohne effizienten Bereinigungsprozess kann ein Überlauf des Zwischenspeichers auftreten, in dem die Registrierungen gespeichert werden, was den Absturz des Resolverdiensts zur Folge haben kann.  
  
 Der <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> versieht jeden Datensatz mit einer Ablaufzeit (DateTime) und speichert diese Information zusammen mit dem Datensatz. Anhand der Ablaufzeit werden veraltete Datensätze durch den Dienst erkannt. Eine solche Vorgehensweise empfiehlt sich auch bei benutzerdefinierten Implementierungen.  
  
## <a name="refreshinterval-and-cleanupinterval"></a>RefreshInterval und CleanupInterval  
 Mit der `RefreshInterval`-Eigenschaft des <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> wird die Gültigkeitsdauer von Registrierungsdatensätzen in der Registrierungssuchtabelle des Diensts definiert. Ist die für diese Eigenschaft angegebene Zeit für einen bestimmten Datensatz abgelaufen, ist dieser Datensatz veraltet und wird zum Löschen markiert.  
  
 Mithilfe der `CleanupInterval`-Eigenschaft des <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> wird dem Dienst mitgeteilt, wie häufig veraltete Registrierungsdatensätze gesucht und gelöscht werden sollen. Das `CleanupInterval` sollte auf eine Zeit festgelegt werden, die mindestens dem für den Dienst festgelegten `RefreshInterval` entspricht.  
  
 Wenn Sie einen eigenen Resolverdienst implementieren möchten, müssen Sie eine Wartungsfunktion zum Entfernen veralteter Registrierungsdatensätze schreiben. Dafür stehen verschiedene Möglichkeiten zur Verfügung:  
  
- **Regelmäßige Wartung**: Legen Sie fest, dass ein Timer regelmäßig deaktiviert wird, und durchlaufen Sie den Datenspeicher, um alte Einträge zu löschen. Dieser Ansatz wird vom <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> verwendet.  
  
- **Passives löschen**: anstatt regelmäßig in regelmäßigen Abständen nach veralteten Datensätzen zu suchen, können Sie veraltete Datensätze erkennen und löschen, wenn Ihr Dienst bereits eine andere Funktion ausführt. Dadurch erhöht sich zwar möglicherweise die Antwortzeit für Anforderungen der Resolverclients, andererseits wird in diesem Fall kein Timer benötigt. Darüber hinaus ist diese Methode möglicherweise effizienter, wenn voraussichtlich nur wenige Knoten das Netz ohne Aufruf von `Unregister` verlassen.  
  
## <a name="registrationlifetime-and-refresh"></a>RegistrationLifetime und Refresh  
 Wenn sich ein Knoten bei einem Resolverdienst registriert, erhält er vom Dienst ein <xref:System.ServiceModel.PeerResolvers.RegisterResponseInfo>-Objekt. Dieses Objekt besitzt eine `RegistrationLifetime`-Eigenschaft, mit der dem Knoten die verbleibende Zeit bis zum Ablauf der Registrierung und damit bis zur Entfernung durch den Resolverdienst angegeben wird. Beispiel: Beträgt die `RegistrationLifetime` zwei Minuten, muss durch den Knoten in weniger als zwei Minuten ein Aufruf von `Refresh` erfolgen, damit der Datensatz nicht als veraltet gilt und gelöscht wird. Erhält der Resolverdienst eine `Refresh`-Anforderung, sucht er den Datensatz und setzt die Ablaufzeit zurück. Durch die Refresh-Anforderung wird ein <xref:System.ServiceModel.PeerResolvers.RefreshResponseInfo>-Objekt mit einer `RegistrationLifetime`-Eigenschaft zurückgegeben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Peerresolver](peer-resolvers.md)
