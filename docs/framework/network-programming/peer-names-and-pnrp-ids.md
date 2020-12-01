---
title: Peernamen und PNRP-IDs
ms.date: 03/30/2017
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
ms.openlocfilehash: a56200d599d417dac549af000b35024338d43796
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239223"
---
# <a name="peer-names-and-pnrp-ids"></a>Peernamen und PNRP-IDs

Ein Peername steht für einen Endpunkt für die Kommunikation, der ein Computer, ein Benutzer, eine Gruppe, ein Dienst oder alles sein kein, was einem Peer zugeordnet ist, das in eine IPv6-Adresse aufgelöst werden kann. Das Peer Name Resolution-Protokoll (PNRP) nimmt den statistisch eindeutigen Peernamen zur Erstellung einer PNRP-ID an, die zur Identifikation von Cloudelementen verwendet wird.  
  
## <a name="peer-names"></a>Peernamen  

 Peernamen können unsicher oder gesichert gespeichert werden. Unsichere Namen sind nur Textzeichenfolgen, die den Gefahren von Spoofing ausgesetzt sind, da jeder einen ungesicherten doppelten Namen registrieren kann. Unsichere Namen werden am besten in privaten oder anderweitig geschützten Netzwerken verwendet. Gesicherte Namen werden durch ein Zertifikat und eine digitale Signatur geschützt. Nur der ursprüngliche Verleger kann den Besitz eines sicheren Namens nachweisen.  
  
 Die Kombination von Cloud und Umfang bietet eine angemessen sichere Umgebung für Peers, die an der PNRP-Aktivität beteiligt sind. Die Verwendung eines sicheren Peernamens garantiert jedoch nicht die Gesamtsicherheit der Netzwerkanwendung. Die Sicherheit der Anwendung ist implementierungsabhängig.  
  
 Gesicherte Peernamen werden nur vom Besitzer registriert und mit einem öffentlichen kryptografischen Schlüssel geschützt. Ein gesicherter Peername ist im Besitz der Peerentität, die über den entsprechenden privaten Schlüssel verfügt. Über die zertifizierte Peeradresse (CPA), die mit dem privaten Schlüssel signiert ist, kann der Besitz nachgewiesen werden. Ein böswilliger Benutzer kann den Besitz eines Peernamen ohne den entsprechenden privaten Schlüssel nicht erstellen.  
  
## <a name="pnrp-ids"></a>PNRP-IDs  

 ![PNRP ID](./media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")  
  
 PNRP-IDs bestehen aus den folgenden Teilen:  
  
- Die höherwertigen 128 Bits sind als Peer-to-Peer-ID (P2P) bekannt. Sie sind ein Hash des Peernamens, der dem Endpunkt zugewiesen ist. Der Peername hat das folgende Format: *Authority.Classifier*. Für sichere Namen ist *Autorität* der Secure-Hash-Algorithmus 1 (SHA1) des öffentlichen Schlüssels des Peernamens in hexadezimalen Zeichen. Für unsichere Namen ist *Autorität* als einzelnes Zeichen „0“ festgelegt. *Klassifizierung* ist eine Zeichenfolge, die die Anwendung identifiziert. Kein Klassifizierer für Peernamen kann länger als 149 Zeichen sein, einschließlich dem `null`-Abschlusszeichen.  
  
- Die niederwertigen 128 Bits werden für die Dienstidentifizierung verwendet. Dies ist eine generierte Zahl, die verschiedene Instanzen der gleichen P2P-ID in der gleichen Cloud identifiziert.  
  
 Diese Kombination von P2P-ID und Dienstidentifizierung ermöglicht die Registrierung mehrerer PNRP-IDs von einem einzelnen Computer aus.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.PeerToPeer.PeerName>
- <xref:System.Net.PeerToPeer>
