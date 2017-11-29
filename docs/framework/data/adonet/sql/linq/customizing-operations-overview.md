---
title: "Anpassen von Operationen: Übersicht"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7653ca137c93da5174e0ddcd1ced8bdfceaa9edc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="d79c5-102">Anpassen von Operationen: Übersicht</span><span class="sxs-lookup"><span data-stu-id="d79c5-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="d79c5-103">Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL für Insert-, Update und Delete-Operationen auf Grundlage der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="d79c5-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="d79c5-104">In der Praxis möchten Sie jedoch in der Regel Ihre eigene Geschäftslogik hinzufügen, um Sicherheit, Validierung etc. zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d79c5-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d79c5-105">Techniken zur Anpassung dieser Operationen zählen den folgende:</span><span class="sxs-lookup"><span data-stu-id="d79c5-105"> techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="d79c5-106">Ladeoptionen</span><span class="sxs-lookup"><span data-stu-id="d79c5-106">Loading Options</span></span>  
 <span data-ttu-id="d79c5-107">In Ihren Abfragen können Sie kontrollieren, wie viele Daten zum Hauptziel abgerufen werden, wenn Sie eine Verbindung zur Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="d79c5-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="d79c5-108">Diese Funktionalität wird zum größten Teil durch Verwendung von <xref:System.Data.Linq.DataLoadOptions> implementiert.</span><span class="sxs-lookup"><span data-stu-id="d79c5-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="d79c5-109">Weitere Informationen finden Sie unter [verzögerte und sofortige laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="d79c5-109">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="d79c5-110">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="d79c5-110">Partial Methods</span></span>  
 <span data-ttu-id="d79c5-111">In seiner Standardzuordnung stellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] partielle Methoden bereit, um Sie bei der Implementierung der Geschäftslogik zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d79c5-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="d79c5-112">Weitere Informationen finden Sie unter [hinzufügen Business Logik von mithilfe von partiellen Methoden](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d79c5-112">For more information, see [Adding Business Logic By Using Partial Methods](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="d79c5-113">Gespeicherte Prozeduren und benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="d79c5-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d79c5-114">unterstützt die Verwendung von gespeicherten Prozeduren und benutzerdefinierte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d79c5-114"> supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="d79c5-115">Gespeicherte Prozeduren werden häufig verwendet, um Operationen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="d79c5-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="d79c5-116">Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d79c5-116">For more information, see [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79c5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d79c5-117">See Also</span></span>  
 [<span data-ttu-id="d79c5-118">Anpassen von INSERT-, Update- und Löschvorgänge</span><span class="sxs-lookup"><span data-stu-id="d79c5-118">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
