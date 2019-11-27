---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349547"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="d6792-102">GetType-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6792-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="d6792-103">Gibt ein <xref:System.Type>-Objekt für den angegebenen Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="d6792-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="d6792-104">Das <xref:System.Type>-Objekt enthält Informationen über den Typ, z. b. seine Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d6792-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6792-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6792-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6792-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6792-106">Parameters</span></span>  
  
|<span data-ttu-id="d6792-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6792-107">Parameter</span></span>|<span data-ttu-id="d6792-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6792-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="d6792-109">Der Name des Typs, für den Sie Informationen wünschen.</span><span class="sxs-lookup"><span data-stu-id="d6792-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6792-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6792-110">Remarks</span></span>  
 <span data-ttu-id="d6792-111">Der `GetType`-Operator gibt das <xref:System.Type>-Objekt für den angegebenen `typename`zurück.</span><span class="sxs-lookup"><span data-stu-id="d6792-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="d6792-112">Sie können den Namen eines beliebigen definierten Typs in `typename`übergeben.</span><span class="sxs-lookup"><span data-stu-id="d6792-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="d6792-113">Hierzu gehören folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="d6792-113">This includes the following:</span></span>  
  
- <span data-ttu-id="d6792-114">Jeder Visual Basic Datentyp, z. b. `Boolean` oder `Date`.</span><span class="sxs-lookup"><span data-stu-id="d6792-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="d6792-115">Alle .NET Framework Klassen, Strukturen, Module oder Schnittstellen, z. b. <xref:System.ArgumentException?displayProperty=nameWithType> oder <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6792-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="d6792-116">Alle Klassen, Strukturen, Module oder Schnittstellen, die von der Anwendung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6792-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="d6792-117">Ein beliebiges Array, das von Ihrer Anwendung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d6792-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="d6792-118">Jeder Delegat, der von der Anwendung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d6792-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="d6792-119">Eine beliebige Enumeration, die von Visual Basic, dem .NET Framework oder der Anwendung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d6792-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="d6792-120">Wenn Sie das Typobjekt einer Objektvariablen erhalten möchten, verwenden Sie die <xref:System.Type.GetType%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="d6792-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="d6792-121">Der `GetType`-Operator kann in den folgenden Situationen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="d6792-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="d6792-122">Sie müssen zur Laufzeit auf die Metadaten für einen Typ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d6792-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="d6792-123">Das <xref:System.Type>-Objekt stellt Metadaten wie Typmember und Bereitstellungs Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="d6792-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="d6792-124">Dies ist z. b. erforderlich, um eine Assembly widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="d6792-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="d6792-125">Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6792-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="d6792-126">Sie möchten zwei Objekt Verweise vergleichen, um festzustellen, ob Sie auf Instanzen desselben Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="d6792-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="d6792-127">Wenn dies der Fall ist, gibt `GetType` Verweise auf dasselbe <xref:System.Type>-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d6792-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6792-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6792-128">Example</span></span>  
 <span data-ttu-id="d6792-129">Die folgenden Beispiele zeigen den verwendeten `GetType`-Operator.</span><span class="sxs-lookup"><span data-stu-id="d6792-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="d6792-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6792-130">See also</span></span>

- [<span data-ttu-id="d6792-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6792-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d6792-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="d6792-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d6792-133">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d6792-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
