---
title: Anpassen von Insert-, Update- und Delete-Operationen
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: ed3de95a8224f0b4d8f3d5d913274417a6879942
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247609"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="0eb1b-102">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="0eb1b-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="0eb1b-103">Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL, um Insert-, Read-, Update und Delete-Operationen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="0eb1b-104">In der Praxis passen Sie die Anwendung i. d. R. an, um die Geschäftsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0eb1b-105">Wenn Sie Visual Studio verwenden, können Sie die objektrelationaler Designer zum Anpassen von INSERT-, Update-und DELETE-Aktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-105">If you are using Visual Studio, you can use the Object Relational Designer to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="0eb1b-106">Dieser Abschnitt beschreibt die Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zur Anpassung von Insert-, Update- und Delete-Operationen in Ihrer Anwendung zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0eb1b-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0eb1b-107">In This Section</span></span>  
 [<span data-ttu-id="0eb1b-108">Anpassen von Vorgängen: Übersicht</span><span class="sxs-lookup"><span data-stu-id="0eb1b-108">Customizing Operations: Overview</span></span>](customizing-operations-overview.md)  
 <span data-ttu-id="0eb1b-109">Beschreibt die verschiedenen Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für das Anpassen von Insert-, Update- und Delete-Operationen zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="0eb1b-110">Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="0eb1b-110">Insert, Update, and Delete Operations</span></span>](insert-update-and-delete-operations.md)  
 <span data-ttu-id="0eb1b-111">Beschreibt die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardverfahren zum Bearbeiten von Datenbankdaten.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="0eb1b-112">Aufgaben der Entwickler beim Überschreiben von Standardverhalten</span><span class="sxs-lookup"><span data-stu-id="0eb1b-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="0eb1b-113">Beschreibt die Rolle des Entwicklers bei der Implementierung von Anforderungen, die nicht von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] durchgesetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="0eb1b-114">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="0eb1b-114">Adding Business Logic By Using Partial Methods</span></span>](adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="0eb1b-115">Beschreibt, wie partielle Methoden verwendet werden, um automatisch generierte Methoden zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0eb1b-115">Describes how to use partial methods to override autogenerated methods.</span></span>
