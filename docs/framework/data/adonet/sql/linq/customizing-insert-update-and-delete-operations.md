---
title: Anpassen von Insert-, Update- und Delete-Operationen
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: 4b846d1e1f737cec85ecda75df5e3f66982def62
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177344"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="2420f-102">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="2420f-102">Customizing Insert, Update, and Delete Operations</span></span>

<span data-ttu-id="2420f-103">Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL, um Insert-, Read-, Update und Delete-Operationen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="2420f-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="2420f-104">In der Praxis passen Sie die Anwendung i. d. R. an, um die Geschäftsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2420f-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2420f-105">Wenn Sie Visual Studio verwenden, können Sie die objektrelationaler Designer zum Anpassen von INSERT-, Update-und DELETE-Aktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2420f-105">If you are using Visual Studio, you can use the Object Relational Designer to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="2420f-106">Dieser Abschnitt beschreibt die Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zur Anpassung von Insert-, Update- und Delete-Operationen in Ihrer Anwendung zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="2420f-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2420f-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2420f-107">In This Section</span></span>  

 [<span data-ttu-id="2420f-108">Anpassen von Vorgängen: Übersicht</span><span class="sxs-lookup"><span data-stu-id="2420f-108">Customizing Operations: Overview</span></span>](customizing-operations-overview.md)  
 <span data-ttu-id="2420f-109">Beschreibt die verschiedenen Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für das Anpassen von Insert-, Update- und Delete-Operationen zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="2420f-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="2420f-110">Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="2420f-110">Insert, Update, and Delete Operations</span></span>](insert-update-and-delete-operations.md)  
 <span data-ttu-id="2420f-111">Beschreibt die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardverfahren zum Bearbeiten von Datenbankdaten.</span><span class="sxs-lookup"><span data-stu-id="2420f-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="2420f-112">Aufgaben der Entwickler beim Überschreiben von Standardverhalten</span><span class="sxs-lookup"><span data-stu-id="2420f-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="2420f-113">Beschreibt die Rolle des Entwicklers bei der Implementierung von Anforderungen, die nicht von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] durchgesetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="2420f-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2420f-114">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="2420f-114">Adding Business Logic By Using Partial Methods</span></span>](adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="2420f-115">Beschreibt, wie partielle Methoden verwendet werden, um automatisch generierte Methoden zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2420f-115">Describes how to use partial methods to override autogenerated methods.</span></span>
