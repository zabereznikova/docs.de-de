---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 37644a9c37ffde084120c5f1e1ee8c87a04ffc3c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371154"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="b5546-102">GetType-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5546-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="b5546-103">Gibt ein- <xref:System.Type> Objekt für den angegebenen Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="b5546-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="b5546-104">Das- <xref:System.Type> Objekt stellt Informationen über den Typ bereit, z. b. seine Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="b5546-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5546-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5546-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5546-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5546-106">Parameters</span></span>  
  
|<span data-ttu-id="b5546-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5546-107">Parameter</span></span>|<span data-ttu-id="b5546-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b5546-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="b5546-109">Der Name des Typs, für den Sie Informationen wünschen.</span><span class="sxs-lookup"><span data-stu-id="b5546-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5546-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b5546-110">Remarks</span></span>  
 <span data-ttu-id="b5546-111">Der- `GetType` Operator gibt das- <xref:System.Type> Objekt für den angegebenen zurück `typename` .</span><span class="sxs-lookup"><span data-stu-id="b5546-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="b5546-112">Sie können den Namen eines beliebigen definierten Typs in übergeben `typename` .</span><span class="sxs-lookup"><span data-stu-id="b5546-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="b5546-113">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="b5546-113">This includes the following:</span></span>  
  
- <span data-ttu-id="b5546-114">Beliebige Visual Basic Datentyp, z `Boolean` . b `Date` . oder.</span><span class="sxs-lookup"><span data-stu-id="b5546-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="b5546-115">Alle .NET Framework Klassen, Strukturen, Module oder Schnittstellen, z <xref:System.ArgumentException?displayProperty=nameWithType> . b <xref:System.Double?displayProperty=nameWithType> . oder.</span><span class="sxs-lookup"><span data-stu-id="b5546-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="b5546-116">Alle Klassen, Strukturen, Module oder Schnittstellen, die von der Anwendung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5546-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="b5546-117">Ein beliebiges Array, das von Ihrer Anwendung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5546-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="b5546-118">Jeder Delegat, der von der Anwendung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5546-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="b5546-119">Eine beliebige Enumeration, die von Visual Basic, dem .NET Framework oder der Anwendung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5546-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="b5546-120">Wenn Sie das Typobjekt einer Objektvariablen erhalten möchten, verwenden Sie die- <xref:System.Type.GetType%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="b5546-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b5546-121">Der- `GetType` Operator kann in den folgenden Situationen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="b5546-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="b5546-122">Sie müssen zur Laufzeit auf die Metadaten für einen Typ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b5546-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="b5546-123">Das <xref:System.Type> -Objekt stellt Metadaten wie Typmember und Bereitstellungs Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="b5546-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="b5546-124">Dies ist z. b. erforderlich, um eine Assembly widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="b5546-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="b5546-125">Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b5546-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="b5546-126">Sie möchten zwei Objekt Verweise vergleichen, um festzustellen, ob Sie auf Instanzen desselben Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="b5546-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="b5546-127">Wenn dies der Fall ist, `GetType` gibt Verweise auf dasselbe <xref:System.Type> Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b5546-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5546-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5546-128">Example</span></span>  
 <span data-ttu-id="b5546-129">Die folgenden Beispiele zeigen den `GetType` verwendeten Operator.</span><span class="sxs-lookup"><span data-stu-id="b5546-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="b5546-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5546-130">See also</span></span>

- [<span data-ttu-id="b5546-131">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5546-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="b5546-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="b5546-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b5546-133">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="b5546-133">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
