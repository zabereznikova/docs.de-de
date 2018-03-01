---
title: GetType-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38a984dce44133936f7f163e6afb20f0f336377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="7c7f2-102">GetType-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c7f2-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="7c7f2-103">Gibt eine <xref:System.Type> Objekt für den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="7c7f2-104">Die <xref:System.Type> Objekt enthält Informationen über den Typ, z. B. seine Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c7f2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c7f2-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c7f2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c7f2-106">Parameters</span></span>  
  
|<span data-ttu-id="7c7f2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c7f2-107">Parameter</span></span>|<span data-ttu-id="7c7f2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c7f2-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="7c7f2-109">Der Name des Typs für die Sie Informationen wünschen.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c7f2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c7f2-110">Remarks</span></span>  
 <span data-ttu-id="7c7f2-111">Die `GetType` Operator gibt den <xref:System.Type> für das angegebene Objekt `typename`.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="7c7f2-112">Sie können den Namen eines beliebigen definierten Typs in übergeben `typename`.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="7c7f2-113">Hierzu gehören folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="7c7f2-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="7c7f2-114">Alle Visual Basic-Datentyp, wie z. B. `Boolean` oder `Date`.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="7c7f2-115">Alle .NET Framework-Klasse, Struktur, Modul oder Schnittstelle, wie z. B. <xref:System.ArgumentException?displayProperty=nameWithType> oder <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="7c7f2-116">Eine beliebige Klasse, Struktur, Modul oder Schnittstelle, die von der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="7c7f2-117">Alle von der Anwendung definiertes Array.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="7c7f2-118">Alle von der Anwendung definierten Delegaten.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="7c7f2-119">Eine Enumeration von Visual Basic, .NET Framework oder der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="7c7f2-120">Wenn Sie das Typobjekt einer Objektvariablen abrufen möchten, verwenden Sie die <xref:System.Type.GetType%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="7c7f2-121">Die `GetType` Operator kann in folgenden Situationen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="7c7f2-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="7c7f2-122">Sie müssen die Metadaten für einen Typ zur Laufzeit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="7c7f2-123">Die <xref:System.Type> Objekt liefert Metadaten, z. B. Typmember und Bereitstellungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="7c7f2-124">Dies ist erforderlich, z. B. über eine Assembly widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="7c7f2-125">Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="7c7f2-126">Vergleichen von zwei Objektverweise, um festzustellen, ob sie auf Instanzen des gleichen Typs verweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="7c7f2-127">Wenn dies der Fall, `GetType` gibt Verweise auf die gleiche <xref:System.Type> Objekt.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c7f2-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c7f2-128">Example</span></span>  
 <span data-ttu-id="7c7f2-129">Das folgende Beispiel zeigt die `GetType` Operator verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c7f2-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7c7f2-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c7f2-130">See Also</span></span>  
 [<span data-ttu-id="7c7f2-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c7f2-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="7c7f2-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="7c7f2-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="7c7f2-133">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7c7f2-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
