---
title: GetType-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840320"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="39b08-102">GetType-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39b08-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="39b08-103">Gibt eine <xref:System.Type> Objekt für den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="39b08-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="39b08-104">Die <xref:System.Type> Objekt enthält Informationen über die Art, wie z. B. die Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="39b08-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b08-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="39b08-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="39b08-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="39b08-106">Parameters</span></span>  
  
|<span data-ttu-id="39b08-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="39b08-107">Parameter</span></span>|<span data-ttu-id="39b08-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b08-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="39b08-109">Der Name des Typs für die Sie Informationen wünschen.</span><span class="sxs-lookup"><span data-stu-id="39b08-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39b08-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39b08-110">Remarks</span></span>  
 <span data-ttu-id="39b08-111">Die `GetType` -Operator gibt die <xref:System.Type> -Objekt für die angegebene `typename`.</span><span class="sxs-lookup"><span data-stu-id="39b08-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="39b08-112">Sie können den Namen eines beliebigen definierten Typs in übergeben `typename`.</span><span class="sxs-lookup"><span data-stu-id="39b08-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="39b08-113">Hierzu gehören folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="39b08-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="39b08-114">Geben Sie alle Visual Basic-Daten, z. B. `Boolean` oder `Date`.</span><span class="sxs-lookup"><span data-stu-id="39b08-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="39b08-115">Alle .NET Framework-Klasse, Struktur, Modul oder Schnittstelle, wie z. B. <xref:System.ArgumentException?displayProperty=nameWithType> oder <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39b08-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="39b08-116">Jede Klasse, Struktur, Modul oder Schnittstelle, die von der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="39b08-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="39b08-117">Ein Array, das von der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="39b08-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="39b08-118">Jeder Delegat, der von der Anwendung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="39b08-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="39b08-119">Enumerationen von Visual Basic, .NET Framework oder der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="39b08-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="39b08-120">Wenn Sie das Type-Objekt einer Objektvariablen abrufen möchten, verwenden Sie die <xref:System.Type.GetType%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="39b08-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="39b08-121">Die `GetType` Operator kann in folgenden Situationen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="39b08-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="39b08-122">Sie müssen die Metadaten für einen Typ zur Laufzeit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="39b08-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="39b08-123">Die <xref:System.Type> Objekt liefert Metadaten wie z. B. Typmember und Bereitstellungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="39b08-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="39b08-124">Sie benötigen diesen, z. B. über eine Assembly widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="39b08-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="39b08-125">Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39b08-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="39b08-126">Sie möchten vergleichen zwei Objektverweise, um festzustellen, ob sie mit Instanzen des gleichen Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="39b08-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="39b08-127">Wenn dies der Fall, `GetType` gibt Verweise auf die gleiche <xref:System.Type> Objekt.</span><span class="sxs-lookup"><span data-stu-id="39b08-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39b08-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39b08-128">Example</span></span>  
 <span data-ttu-id="39b08-129">Die folgenden Beispiele zeigen die `GetType` -Operator in verwenden.</span><span class="sxs-lookup"><span data-stu-id="39b08-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="39b08-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39b08-130">See also</span></span>

- [<span data-ttu-id="39b08-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39b08-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="39b08-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="39b08-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="39b08-133">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39b08-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
