---
title: PNRP in der Anwendungsentwicklung
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b085604d7d20eb9222507b4820be219ffeae4726
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395735"
---
# <a name="pnrp-in-application-development"></a><span data-ttu-id="356e2-102">PNRP in der Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="356e2-102">PNRP in Application Development</span></span>
<span data-ttu-id="356e2-103">In Windows Vista können Netzwerkanwendungen über eine vereinfachte PNRP-Anwendungsprogrammierschnittstelle (application programming interface – API) auf Funktionen zur Veröffentlichung und Auflösung von Namen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="356e2-103">In Windows Vista, networking applications can access name publication and resolution functions through a simplified PNRP application programming interface (API).</span></span>  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a><span data-ttu-id="356e2-104">Implementieren des Peer Name Resolution-Protokolls</span><span class="sxs-lookup"><span data-stu-id="356e2-104">Implementing the Peer Name Resolution Protocol</span></span>  
 <span data-ttu-id="356e2-105">Bei der vereinfachten PNRP-API werden Clouds nicht explizit für die Namens- und Adressregistrierung angegeben. Die PNRP-Komponente bestimmt automatisch, welchen passenden Clouds beigetreten werden soll und welche Adressen in diesen veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="356e2-105">With the simplified PNRP API, clouds are not explicitly specified to register the name and addresses; the PNRP component automatically determines the appropriate clouds to join and the addresses to publish within the clouds.</span></span>  
  
 <span data-ttu-id="356e2-106">Für die sehr stark vereinfachte PNRP-Namensauflösung in Windows Vista werden PNRP-Namen nun in die Windows Sockets-Funktion getaddrinfo() integriert.</span><span class="sxs-lookup"><span data-stu-id="356e2-106">For highly simplified PNRP name resolution in Windows Vista, PNRP names are now integrated into the getaddrinfo() Windows Sockets function.</span></span> <span data-ttu-id="356e2-107">Namen lassen sich mithilfe von PNRP in eine IPv6-Adresse aufzulösen. Dazu können Anwendungen mit der Funktion getaddrinfo() den vollqualifizierten Domänennamen (Fully Qualified Domain Name – FQDN) „name-prnp.net“ verwenden. „name“ steht hier für den aufzulösenden Peernamen.</span><span class="sxs-lookup"><span data-stu-id="356e2-107">To use PNRP to resolve a name to an IPv6 address, applications can use the getaddrinfo() function to resolve the Fully Qualified Domain Name (FQDN) name.prnp.net, in which name is peer name being resolved.</span></span> <span data-ttu-id="356e2-108">Die Domain „pnrp.net“ ist in Windows Vista für die Auflösung von PNRP-Namen reserviert.</span><span class="sxs-lookup"><span data-stu-id="356e2-108">The pnrp.net domain is a reserved domain in Windows Vista for PNRP name resolution.</span></span>  
  
 <span data-ttu-id="356e2-109">Die Nachrichtenübergabe zwischen Peer-zu-Peer-Anwendungen wird weiterhin von der zu Grunde liegenden Architektur übernommen, z.B. PeerChannel oder der WCF-Funktion für [umfangreiche Daten und Streaming](http://go.microsoft.com/fwlink/?LinkID=179652).</span><span class="sxs-lookup"><span data-stu-id="356e2-109">Message passing between PeerToPeer applications is still handled by underlying architectures such as PeerChannel and WCF [Large Data and Streaming](http://go.microsoft.com/fwlink/?LinkID=179652).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="356e2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="356e2-110">See Also</span></span>  
 <xref:System.Net.PeerToPeer>
