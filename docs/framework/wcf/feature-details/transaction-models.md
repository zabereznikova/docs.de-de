---
title: Transaktionsmodelle
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: d6c78a5342bf19d19308352cddc241f436bfcb3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745322"
---
# <a name="transaction-models"></a><span data-ttu-id="e1fdd-102">Transaktionsmodelle</span><span class="sxs-lookup"><span data-stu-id="e1fdd-102">Transaction Models</span></span>
<span data-ttu-id="e1fdd-103">In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="e1fdd-104">Bei der Verwendung von Transaktionen in Windows Communication Foundation (WCF) ist es wichtig zu verstehen, dass Sie nicht zwischen unterschiedlichen Transaktions Modellen auswählen, sondern stattdessen auf unterschiedlichen Ebenen eines integrierten und konsistenten Modells arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="e1fdd-105">In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="e1fdd-106">Windows-Kommunikationfoundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e1fdd-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="e1fdd-107">Die Transaktionsunterstützung in WCF ermöglicht das Schreiben von Transaktions Diensten.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="e1fdd-108">Außerdem können Anwendungen mit der Unterstützung des WS-AtomicTransaction (WS-AT)-Protokolls Transaktionen an Webdienste übertragen, die entweder mithilfe von WCF oder von Drittanbieter Technologie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="e1fdd-109">In einem WCF-Dienst oder einer WCF-Anwendung stellen WCF-Transaktions Features Attribute und Konfigurationen bereit, um deklarativ anzugeben, wie und wann die infrastrukturtransaktionen erstellen, Fluss und synchronisieren soll.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="e1fdd-110">System.Transactions-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e1fdd-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="e1fdd-111">Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="e1fdd-112">Weitere Informationen zum Erstellen einer Transaktions Anwendung mit diesen beiden Modellen finden Sie unter [Schreiben einer transaktionalen Anwendung](https://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="e1fdd-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="e1fdd-113">In einem WCF-Dienst oder einer WCF-Anwendung stellt <xref:System.Transactions> das Programmiermodell zum Erstellen von Transaktionen in einer Client Anwendung und zur expliziten Interaktion mit einer Transaktion in einem Dienst bereit.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="e1fdd-114">MSDTC-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e1fdd-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="e1fdd-115">Der Microsoft Distributed Transaction Coordinator (MSDTC) ist ein Transaktions-Manager, der verteilte Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="e1fdd-116">Weitere Informationen finden Sie in der [DTC-Programmier Referenz](https://docs.microsoft.com/previous-versions/windows/desktop/ms686108(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e1fdd-116">For more information, see the [DTC Programmer's Reference](https://docs.microsoft.com/previous-versions/windows/desktop/ms686108(v=vs.85)).</span></span>  
  
 <span data-ttu-id="e1fdd-117">In einem WCF-Dienst oder einer WCF-Anwendung bietet MSDTC die Infrastruktur für die Koordination von Transaktionen, die in einem Client oder Dienst erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e1fdd-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
