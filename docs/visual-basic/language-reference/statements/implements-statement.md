---
title: Implements-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 7fb43934d8c200ff29b1caf63cec830b2c6633ce
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404549"
---
# <a name="implements-statement"></a><span data-ttu-id="8ca92-102">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8ca92-102">Implements Statement</span></span>
<span data-ttu-id="8ca92-103">Gibt eine oder mehrere Schnittstellen oder Schnittstellenmember an, die in der Klassen-oder Struktur Definition implementiert werden müssen, in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ca92-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ca92-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="8ca92-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="8ca92-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="8ca92-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8ca92-106">Required.</span></span> <span data-ttu-id="8ca92-107">Eine Schnittstelle, deren Eigenschaften, Prozeduren und Ereignisse von entsprechenden Membern in der Klasse oder Struktur implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8ca92-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="8ca92-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8ca92-108">Required.</span></span> <span data-ttu-id="8ca92-109">Der Member einer Schnittstelle, die implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8ca92-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ca92-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8ca92-110">Remarks</span></span>  
 <span data-ttu-id="8ca92-111">Eine Schnittstelle ist eine Auflistung von Prototypen, die die Elemente (Eigenschaften, Prozeduren und Ereignisse) darstellen, die die Schnittstelle kapselt.</span><span class="sxs-lookup"><span data-stu-id="8ca92-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="8ca92-112">Schnittstellen enthalten nur die Deklarationen für Member. Klassen und Strukturen implementieren diese Member.</span><span class="sxs-lookup"><span data-stu-id="8ca92-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="8ca92-113">Weitere Informationen finden Sie unter [Schnittstellen](../../programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="8ca92-113">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="8ca92-114">Die- `Implements` Anweisung muss direkt auf die- `Class` oder-Anweisung folgen `Structure` .</span><span class="sxs-lookup"><span data-stu-id="8ca92-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="8ca92-115">Wenn Sie eine Schnittstelle implementieren, müssen alle in der Schnittstelle deklarierten Member implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8ca92-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="8ca92-116">Das Weglassen eines Members wird als Syntax Fehler betrachtet.</span><span class="sxs-lookup"><span data-stu-id="8ca92-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="8ca92-117">Zum Implementieren eines einzelnen Members geben Sie das [implementierte](implements-clause.md) Schlüsselwort (das von der-Anweisung getrennt ist) an, `Implements` Wenn Sie den Member in der Klasse oder Struktur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8ca92-117">To implement an individual member, you specify the [Implements](implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="8ca92-118">Weitere Informationen finden Sie unter [Schnittstellen](../../programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="8ca92-118">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="8ca92-119">Klassen können [private](../modifiers/private.md) Implementierungen von Eigenschaften und Prozeduren verwenden, aber auf diese Member kann nur zugegriffen werden, indem eine Instanz der implementierenden Klasse in eine Variable umgewandelt wird, die als der Typ der Schnittstelle deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="8ca92-119">Classes can use [Private](../modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ca92-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ca92-120">Example</span></span>  
 <span data-ttu-id="8ca92-121">Im folgenden Beispiel wird gezeigt, wie die-Anweisung verwendet wird `Implements` , um Member einer Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="8ca92-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="8ca92-122">Er definiert eine Schnittstelle `ICustomerInfo` mit dem Namen mit einem Ereignis, einer Eigenschaft und einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8ca92-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="8ca92-123">Die-Klasse implementiert alle Member, die `customerInfo` in der-Schnittstelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="8ca92-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="8ca92-124">Beachten Sie, dass die-Klasse `customerInfo` die- `Implements` Anweisung in einer separaten Quell Code Zeile verwendet, um anzugeben, dass die-Klasse alle Member der- `ICustomerInfo` Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="8ca92-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="8ca92-125">Dann verwendet jedes Element in der-Klasse das- `Implements` Schlüsselwort als Teil seiner Member-Deklaration, um anzugeben, dass dieses Schnittstellenmember implementiert.</span><span class="sxs-lookup"><span data-stu-id="8ca92-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ca92-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ca92-126">Example</span></span>  
 <span data-ttu-id="8ca92-127">Die folgenden zwei Prozeduren zeigen, wie Sie die im vorherigen Beispiel implementierte-Schnittstelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8ca92-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="8ca92-128">Fügen Sie dem Projekt diese Prozeduren hinzu, und nennen Sie die-Prozedur, um die Implementierung zu testen `testImplements` .</span><span class="sxs-lookup"><span data-stu-id="8ca92-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="8ca92-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ca92-129">See also</span></span>

- [<span data-ttu-id="8ca92-130">Implementiert</span><span class="sxs-lookup"><span data-stu-id="8ca92-130">Implements</span></span>](implements-clause.md)
- [<span data-ttu-id="8ca92-131">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8ca92-131">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="8ca92-132">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8ca92-132">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
