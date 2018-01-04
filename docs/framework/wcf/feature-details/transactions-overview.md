---
title: "Übersicht über Windows Communication Foundation-Transaktionen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fb90d0f93e9bdf7dd9779ffd5d4b1288ba56e7a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-transactions-overview"></a><span data-ttu-id="0e5d0-102">Übersicht über Windows-Kommunikationfoundation-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="0e5d0-102">Windows Communication Foundation Transactions Overview</span></span>
<span data-ttu-id="0e5d0-103">Transaktionen stellen eine Möglichkeit dar, mehrere Aktionen oder Vorgänge in eine einzelne unteilbare Ausführungseinheit zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-103">Transactions provide a way to group a set of actions or operations into a single indivisible unit of execution.</span></span> <span data-ttu-id="0e5d0-104">Eine Transaktion ist eine Auflistung von Vorgängen mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0e5d0-104">A transaction is a collection of operations with the following properties:</span></span>  
  
-   <span data-ttu-id="0e5d0-105">Unteilbarkeit.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-105">Atomicity.</span></span> <span data-ttu-id="0e5d0-106">Dadurch wird sichergestellt, dass entweder alle unter einer bestimmten Transaktion ausgeführten Updates übernommen und dauerhaft gemacht werden oder abgebrochen und in ihren vorherigen Zustand zurückversetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-106">This ensures that either all of the updates completed under a specific transaction are committed and made durable or they are all aborted and rolled back to their previous state.</span></span>  
  
-   <span data-ttu-id="0e5d0-107">Konsistenz.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-107">Consistency.</span></span> <span data-ttu-id="0e5d0-108">Dadurch wird sichergestellt, dass die unter einer bestimmten Transaktion vorgenommenen Änderungen eine Transformation von einem konsistenten Zustand zu einem anderen darstellen.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-108">This guarantees that the changes made under a transaction represent a transformation from one consistent state to another.</span></span> <span data-ttu-id="0e5d0-109">Beispielsweise ändert eine Transaktion, bei der Geld von einem Girokonto auf ein Sparkonto überwiesen wird, die Geldmenge auf dem Bankkonto insgesamt nicht.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-109">For example, a transaction that transfers money from a checking account to a savings account does not change the amount of money in the overall bank account.</span></span>  
  
-   <span data-ttu-id="0e5d0-110">Isolation</span><span class="sxs-lookup"><span data-stu-id="0e5d0-110">Isolation.</span></span> <span data-ttu-id="0e5d0-111">Dadurch wird verhindert, dass eine Transaktion ungespeicherte Änderungen beobachtet, die zu anderen gleichzeitigen Transaktionen gehören.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-111">This prevents a transaction from observing uncommitted changes belonging to other concurrent transactions.</span></span> <span data-ttu-id="0e5d0-112">Isolation bietet eine Abstraktion von Parallelität und stellt gleichzeitig sicher, dass eine Transaktion keine unerwarteten Auswirkungen auf die Ausführung einer anderen Transaktion haben kann.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-112">Isolation provides an abstraction of concurrency while ensuring one transaction cannot have an unexpected impact on the execution of another transaction.</span></span>  
  
-   <span data-ttu-id="0e5d0-113">Dauerhaftigkeit.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-113">Durability.</span></span> <span data-ttu-id="0e5d0-114">Dies bedeutet, dass Updates verwalteter Ressourcen (z. B. eines Datensatzes in einer Datenbank) nach der Ausführung bei Fehlern dauerhaft sind.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-114">This means that once committed, updates to managed resources (such as a database record) will be persistent in the face of failures.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="0e5d0-115"> bietet einen umfangreichen Satz an Funktionen, mit denen Sie verteilte Transaktionen in Ihrer Webdienstanwendung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-115"> provides a rich set of features that enable you to create distributed transactions in your Web service application.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0e5d0-116"> implementiert die Unterstützung für das WS-AtomicTransaction (WS-AT)-Protokoll, mit dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen Transaktionen zu interoperablen Anwendungen ausführen können, z. B. zu mithilfe von Drittanbietertechnologie erstellten interoperablen Webdiensten.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-116"> implements support for the WS-AtomicTransaction (WS-AT) protocol that enables [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to flow transactions to interoperable applications, such as interoperable Web services built using third-party technology.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0e5d0-117"> implementiert außerdem die Unterstützung für das OLE Transactions-Protokoll, das in Szenarien verwendet werden kann, in denen keine Interop-Funktionalität zum Aktivieren des Transaktionsflusses erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-117"> also implements support for the OLE Transactions protocol, which can be used in scenarios where you do not need interop functionality to enable transaction flow.</span></span>  
  
 <span data-ttu-id="0e5d0-118">Sie können eine Anwendungskonfigurationsdatei verwenden, um Bindungen für das Aktivieren bzw. Deaktivieren des Transaktionsflusses zu konfigurieren sowie das gewünschte Transaktionsprotokoll auf einer Bindung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-118">You can use an application configuration file to configure bindings to enable or disable transaction flow, as well as set the desired transaction protocol on a binding.</span></span> <span data-ttu-id="0e5d0-119">Außerdem können Sie mit der Konfigurationsdatei Transaktionstimeouts auf Dienstebene festlegen.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-119">In addition, you can set transaction time-outs at the service level using the configuration file.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="0e5d0-120">[Aktivieren des Transaktionsflusses](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="0e5d0-120"> [Enabling Transaction Flow](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
 <span data-ttu-id="0e5d0-121">Mithilfe von Transaktionsattributen im <xref:System.ServiceModel>-Namespace können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="0e5d0-121">Transaction attributes in the <xref:System.ServiceModel> namespace allow you to do the following:</span></span>  
  
-   <span data-ttu-id="0e5d0-122">Konfigurieren von Transaktionstimeouts und Isolationsstufenfilterung mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-122">Configure transaction time-outs and isolation-level filtering using the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="0e5d0-123">Aktivieren der Transaktionsfunktionalität und Konfigurieren des Transaktionsabschlussverhaltens mit dem <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-123">Enable transactions functionality and configure transaction completion behavior using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="0e5d0-124">Verwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und <xref:System.ServiceModel.OperationContractAttribute>-Attributs für eine Vertragsmethode, um den Transaktionsfluss zu erfordern, zuzulassen oder zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="0e5d0-124">Use the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes on a contract method to require, allow or deny transaction flow.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="0e5d0-125">[ServiceModel-Transaktionsattribute](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="0e5d0-125"> [ServiceModel Transaction Attributes](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5d0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e5d0-126">See Also</span></span>  
 [<span data-ttu-id="0e5d0-127">ServiceModel-Transaktionsattribute</span><span class="sxs-lookup"><span data-stu-id="0e5d0-127">ServiceModel Transaction Attributes</span></span>](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [<span data-ttu-id="0e5d0-128">Aktivieren des Transaktionsdatenflusses</span><span class="sxs-lookup"><span data-stu-id="0e5d0-128">Enabling Transaction Flow</span></span>](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
