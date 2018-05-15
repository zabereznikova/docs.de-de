---
title: GetType-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 581f576222eb149aede841a5da7a0e5f38c77b58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="39f84-102">GetType-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39f84-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="39f84-103">Gibt eine <xref:System.Type> Objekt für den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="39f84-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="39f84-104">Die <xref:System.Type> Objekt enthält Informationen über den Typ, z. B. seine Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="39f84-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f84-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="39f84-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39f84-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="39f84-106">Parameters</span></span>  
  
|<span data-ttu-id="39f84-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="39f84-107">Parameter</span></span>|<span data-ttu-id="39f84-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39f84-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="39f84-109">Der Name des Typs für die Sie Informationen wünschen.</span><span class="sxs-lookup"><span data-stu-id="39f84-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39f84-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39f84-110">Remarks</span></span>  
 <span data-ttu-id="39f84-111">Die `GetType` Operator gibt den <xref:System.Type> für das angegebene Objekt `typename`.</span><span class="sxs-lookup"><span data-stu-id="39f84-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="39f84-112">Sie können den Namen eines beliebigen definierten Typs in übergeben `typename`.</span><span class="sxs-lookup"><span data-stu-id="39f84-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="39f84-113">Hierzu gehören folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="39f84-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="39f84-114">Alle Visual Basic-Datentyp, wie z. B. `Boolean` oder `Date`.</span><span class="sxs-lookup"><span data-stu-id="39f84-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="39f84-115">Alle .NET Framework-Klasse, Struktur, Modul oder Schnittstelle, wie z. B. <xref:System.ArgumentException?displayProperty=nameWithType> oder <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39f84-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="39f84-116">Eine beliebige Klasse, Struktur, Modul oder Schnittstelle, die von der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="39f84-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="39f84-117">Alle von der Anwendung definiertes Array.</span><span class="sxs-lookup"><span data-stu-id="39f84-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="39f84-118">Alle von der Anwendung definierten Delegaten.</span><span class="sxs-lookup"><span data-stu-id="39f84-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="39f84-119">Eine Enumeration von Visual Basic, .NET Framework oder der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="39f84-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="39f84-120">Wenn Sie das Typobjekt einer Objektvariablen abrufen möchten, verwenden Sie die <xref:System.Type.GetType%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="39f84-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="39f84-121">Die `GetType` Operator kann in folgenden Situationen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="39f84-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="39f84-122">Sie müssen die Metadaten für einen Typ zur Laufzeit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="39f84-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="39f84-123">Die <xref:System.Type> Objekt liefert Metadaten, z. B. Typmember und Bereitstellungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="39f84-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="39f84-124">Dies ist erforderlich, z. B. über eine Assembly widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="39f84-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="39f84-125">Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39f84-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="39f84-126">Vergleichen von zwei Objektverweise, um festzustellen, ob sie auf Instanzen des gleichen Typs verweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="39f84-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="39f84-127">Wenn dies der Fall, `GetType` gibt Verweise auf die gleiche <xref:System.Type> Objekt.</span><span class="sxs-lookup"><span data-stu-id="39f84-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39f84-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39f84-128">Example</span></span>  
 <span data-ttu-id="39f84-129">Das folgende Beispiel zeigt die `GetType` Operator verwendet.</span><span class="sxs-lookup"><span data-stu-id="39f84-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="39f84-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39f84-130">See Also</span></span>  
 [<span data-ttu-id="39f84-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39f84-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="39f84-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="39f84-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="39f84-133">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39f84-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
