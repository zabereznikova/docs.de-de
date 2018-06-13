---
title: Transaktionsmodelle
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 9efe8c6994cc80957b707bbae0885a3c5896f70a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499023"
---
# <a name="transaction-models"></a><span data-ttu-id="db733-102">Transaktionsmodelle</span><span class="sxs-lookup"><span data-stu-id="db733-102">Transaction Models</span></span>
<span data-ttu-id="db733-103">In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db733-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="db733-104">Wenn Sie Transaktionen in der Windows Communication Foundation (WCF) verwenden, ist es wichtig zu verstehen, dass Sie keine zwischen verschiedenen Entscheidung sind, sondern eher auf verschiedenen Ebenen eines integrierten und konsistenten Modells ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="db733-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="db733-105">In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db733-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="db733-106">Windows-Kommunikationfoundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="db733-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="db733-107">Die Unterstützung von Transaktionen in WCF ermöglicht, dass das Schreiben von Transaktionsdiensten.</span><span class="sxs-lookup"><span data-stu-id="db733-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="db733-108">Darüber hinaus können Anwendungen durch die Unterstützung für das WS-AtomicTransaction (WS-AT)-Protokoll, Transaktionen an Webdienste, die mit WCF oder drittanbietertechnologie erstellten fließen.</span><span class="sxs-lookup"><span data-stu-id="db733-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="db733-109">Geben Sie in einem WCF-Dienst oder Anwendung sind WCF-Transaktion-Funktionen Attribute und die Konfiguration für deklarativ angeben, wie und wann die Infrastruktur sollte erstellen, übertragen und Transaktionen zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="db733-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="db733-110">System.Transactions-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="db733-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="db733-111">Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="db733-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="db733-112">Weitere Informationen zur Vorgehensweise beim Erstellen einer transaktionsanwendung mit diesen beiden Modellen finden Sie unter [Erstellen einer Transaktionsanwendung](http://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="db733-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="db733-113">In einem WCF-Dienst oder Anwendung <xref:System.Transactions> stellt das Programmiermodell zum Erstellen von Transaktionen im Rahmen einer Clientanwendung und für die Interaktion mit einer Transaktion explizit, wenn innerhalb eines Diensts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="db733-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="db733-114">MSDTC-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="db733-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="db733-115">Der Microsoft Distributed Transaction Coordinator (MSDTC) ist ein Transaktions-Manager, der verteilte Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db733-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="db733-116">Weitere Informationen finden Sie unter der [DTC-Programmierreferenz](http://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="db733-116">For more information, see the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="db733-117">In einem WCF-Dienst oder Anwendung sind bietet MSDTC die Infrastruktur für die Koordinierung von Transaktionen, die innerhalb eines Clients oder Diensts erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="db733-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
