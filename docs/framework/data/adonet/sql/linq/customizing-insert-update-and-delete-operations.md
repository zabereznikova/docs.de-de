---
title: Anpassen von Insert-, Update- und Delete-Operationen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 410385d1689a9fd15a1399411f601e407d590830
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="32302-102">Anpassen von Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="32302-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="32302-103">Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL, um Insert-, Read-, Update und Delete-Operationen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="32302-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="32302-104">In der Praxis passen Sie die Anwendung i. d. R. an, um die Geschäftsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="32302-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32302-105">Wenn Sie Visual Studio verwenden, können Sie mithilfe der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Einfügen anpassen möchten, aktualisieren und löschen-Aktionen.</span><span class="sxs-lookup"><span data-stu-id="32302-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="32302-106">Dieser Abschnitt beschreibt die Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zur Anpassung von Insert-, Update- und Delete-Operationen in Ihrer Anwendung zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="32302-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32302-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="32302-107">In This Section</span></span>  
 [<span data-ttu-id="32302-108">Anpassen von Operationen: Übersicht</span><span class="sxs-lookup"><span data-stu-id="32302-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="32302-109">Beschreibt die verschiedenen Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für das Anpassen von Insert-, Update- und Delete-Operationen zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="32302-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="32302-110">Insert-, Update- und Delete-Operationen</span><span class="sxs-lookup"><span data-stu-id="32302-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="32302-111">Beschreibt die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardverfahren zum Bearbeiten von Datenbankdaten.</span><span class="sxs-lookup"><span data-stu-id="32302-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="32302-112">Aufgaben der Entwickler beim Überschreiben von Standardverhalten</span><span class="sxs-lookup"><span data-stu-id="32302-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="32302-113">Beschreibt die Rolle des Entwicklers bei der Implementierung von Anforderungen, die nicht von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] durchgesetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="32302-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="32302-114">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="32302-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="32302-115">Beschreibt, wie partielle Methoden verwendet werden, um automatisch generierte Methoden zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="32302-115">Describes how to use partial methods to override autogenerated methods.</span></span>
