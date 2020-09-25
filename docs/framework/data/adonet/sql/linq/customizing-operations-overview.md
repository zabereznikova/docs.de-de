---
title: 'Anpassen von Vorgängen: Übersicht'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: d4d375716e3199afcbbb9bbd8b8b04867ca0e5fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173522"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="a8c1f-102">Anpassen von Vorgängen: Übersicht</span><span class="sxs-lookup"><span data-stu-id="a8c1f-102">Customizing Operations: Overview</span></span>

<span data-ttu-id="a8c1f-103">Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL für Insert-, Update und Delete-Operationen auf Grundlage der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="a8c1f-104">In der Praxis möchten Sie jedoch in der Regel Ihre eigene Geschäftslogik hinzufügen, um Sicherheit, Validierung etc. zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a8c1f-105">zu den Techniken, mit denen diese Vorgänge angepasst werden, gehören die folgenden.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-105">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="a8c1f-106">Ladeoptionen</span><span class="sxs-lookup"><span data-stu-id="a8c1f-106">Loading Options</span></span>  

 <span data-ttu-id="a8c1f-107">In Ihren Abfragen können Sie kontrollieren, wie viele Daten zum Hauptziel abgerufen werden, wenn Sie eine Verbindung zur Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="a8c1f-108">Diese Funktionalität wird zum größten Teil durch Verwendung von <xref:System.Data.Linq.DataLoadOptions> implementiert.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="a8c1f-109">Weitere Informationen finden Sie unter [Verzögertes im Vergleich zu unmittelbarem laden](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="a8c1f-109">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="a8c1f-110">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="a8c1f-110">Partial Methods</span></span>  

 <span data-ttu-id="a8c1f-111">In seiner Standardzuordnung stellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] partielle Methoden bereit, um Sie bei der Implementierung der Geschäftslogik zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="a8c1f-112">Weitere Informationen finden Sie unter [Hinzufügen von Geschäftslogik mithilfe von partiellen Methoden](adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a8c1f-112">For more information, see [Adding Business Logic By Using Partial Methods](adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="a8c1f-113">Gespeicherte Prozeduren und benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="a8c1f-113">Stored Procedures and User-Defined Functions</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a8c1f-114">unterstützt die Verwendung von gespeicherten Prozeduren und benutzerdefinierten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-114">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="a8c1f-115">Gespeicherte Prozeduren werden häufig verwendet, um Operationen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a8c1f-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="a8c1f-116">Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a8c1f-116">For more information, see [Stored Procedures](stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8c1f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8c1f-117">See also</span></span>

- [<span data-ttu-id="a8c1f-118">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="a8c1f-118">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
