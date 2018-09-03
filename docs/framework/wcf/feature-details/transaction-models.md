---
title: Transaktionsmodelle
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43474225"
---
# <a name="transaction-models"></a><span data-ttu-id="61be0-102">Transaktionsmodelle</span><span class="sxs-lookup"><span data-stu-id="61be0-102">Transaction Models</span></span>
<span data-ttu-id="61be0-103">In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61be0-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="61be0-104">Wenn Sie Transaktionen in der Windows Communication Foundation (WCF) verwenden, ist es wichtig zu verstehen, dass Sie sind keine zwischen verschiedenen Transaktionsmodellen getroffen Entscheidung, sondern eher auf verschiedenen Schichten eines integrierten und konsistenten Modells.</span><span class="sxs-lookup"><span data-stu-id="61be0-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="61be0-105">In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61be0-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="61be0-106">Windows-Kommunikationfoundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="61be0-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="61be0-107">Die transaktionsunterstützung in WCF ermöglicht, dass Sie Schreiben von Transaktionsdiensten.</span><span class="sxs-lookup"><span data-stu-id="61be0-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="61be0-108">Darüber hinaus können Anwendungen durch die Unterstützung für das Protokoll WS-AtomicTransaction (WS-AT), Transaktionen an Webdienste integriert mit WCF oder Drittanbieter-Technologie fließen.</span><span class="sxs-lookup"><span data-stu-id="61be0-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="61be0-109">In einem WCF-Dienst oder Anwendung geben WCF-Transaktion-Funktionen, Attribute und die Konfiguration für eine deklarative Angabe, wie und wann die Infrastruktur sollte erstellen, flow und Transaktionen zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="61be0-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="61be0-110">System.Transactions-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="61be0-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="61be0-111">Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="61be0-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="61be0-112">Weitere Informationen zum Erstellen einer transaktionsanwendung mit diesen beiden Modellen finden Sie unter [Erstellen einer Transaktionsanwendung](https://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="61be0-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="61be0-113">In einem WCF-Dienst oder Anwendung <xref:System.Transactions> stellt das Programmiermodell bereit, zum Erstellen von Transaktionen in einer Clientanwendung und für die Interaktion mit einer Transaktion explizit, wenn innerhalb eines Diensts erforderlich.</span><span class="sxs-lookup"><span data-stu-id="61be0-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="61be0-114">MSDTC-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="61be0-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="61be0-115">Der Microsoft Distributed Transaction Coordinator (MSDTC) ist ein Transaktions-Manager, der verteilte Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="61be0-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="61be0-116">Weitere Informationen finden Sie unter den [DTC-Programmierreferenz](https://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="61be0-116">For more information, see the [DTC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="61be0-117">In einem WCF-Dienst oder Anwendung bietet MSDTC die Infrastruktur für die Koordinierung von Transaktionen, die innerhalb eines Clients oder Diensts erstellt.</span><span class="sxs-lookup"><span data-stu-id="61be0-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
