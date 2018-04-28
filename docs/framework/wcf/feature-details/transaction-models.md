---
title: Transaktionsmodelle
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab3baf8cc0bb6af951f6f3e6396b7545d0c6b301
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="transaction-models"></a><span data-ttu-id="5989d-102">Transaktionsmodelle</span><span class="sxs-lookup"><span data-stu-id="5989d-102">Transaction Models</span></span>
<span data-ttu-id="5989d-103">In diesem Thema wird die Beziehung zwischen den Transaktionsprogrammiermodellen und den von Microsoft gebotenen Infrastrukturkomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5989d-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="5989d-104">Beim Einsatz von Transaktionen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist es wichtig zu verstehen, dass keine Entscheidung zwischen verschiedenen Transaktionsmodellen getroffen wird, sondern eher auf verschiedenen Schichten eines integrierten und konsistenten Modells gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="5989d-104">When using transactions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="5989d-105">In den folgenden Abschnitten werden die drei primären Transaktionskomponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5989d-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="5989d-106">Windows-Kommunikationfoundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="5989d-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="5989d-107">Die Transaktionsunterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglicht das Schreiben von Transaktionsdiensten.</span><span class="sxs-lookup"><span data-stu-id="5989d-107">The transaction support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows you write transactional services.</span></span> <span data-ttu-id="5989d-108">Zusätzlich können Anwendungen durch die Unterstützung des WS-AtomicTransaction (WS-AT)-Protokolls Transaktionen an Webdienste übertragen, die entweder über [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] oder die Technologie von Fremdanbietern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5989d-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or third-party technology.</span></span>  
  
 <span data-ttu-id="5989d-109">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten oder -Anwendungen bieten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Transaktionsfunktionen Attribute und die Konfiguration für eine deklarative Angabe, wie und wann die Infrastruktur Transaktionen erstellen, übermitteln oder synchronisieren sollte.</span><span class="sxs-lookup"><span data-stu-id="5989d-109">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="5989d-110">System.Transactions-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="5989d-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="5989d-111">Der Namespace <xref:System.Transactions> bietet sowohl ein explizites Programmiermodell, das auf der Klasse <xref:System.Transactions.Transaction> basiert, als auch ein implizites Programmiermodell, das die Klasse <xref:System.Transactions.TransactionScope> verwendet, in der die Infrastruktur automatisch die Transaktionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5989d-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5989d-112"> zum Erstellen einer transaktionsanwendung mit diesen beiden Modellen finden Sie unter [Erstellen einer Transaktionsanwendung](http://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="5989d-112"> how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="5989d-113">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten oder -Anwendungen bietet <xref:System.Transactions> das Programmiermodell für das Erstellen von Transaktionen im Rahmen einer Clientanwendung und, bei Bedarf, für die spezielle Interaktion mit einer Transaktion in einem Dienst.</span><span class="sxs-lookup"><span data-stu-id="5989d-113">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="5989d-114">MSDTC-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="5989d-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="5989d-115">Der Microsoft Distributed Transaction Coordinator (MSDTC) ist ein Transaktions-Manager, der verteilte Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5989d-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="5989d-116">Weitere Informationen finden Sie unter der [DTC-Programmierreferenz](http://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="5989d-116">For more information, see the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="5989d-117">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten oder -Anwendungen bietet MSDTC die Infrastruktur für die Koordinierung von Transaktionen, die innerhalb eines Clients oder Diensts erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5989d-117">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
