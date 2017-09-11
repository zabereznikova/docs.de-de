---
title: '&lt;value&gt; (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <value>
dev_langs:
- CSharp
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 71c8d5ab2e99291f05ef362960b0eeac969e9de1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="7b219-102">&lt;value&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7b219-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="7b219-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b219-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b219-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b219-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="7b219-105">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7b219-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b219-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b219-106">Remarks</span></span>  
 <span data-ttu-id="7b219-107">Mit dem \<value>-Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="7b219-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="7b219-108">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Entwicklungsumgebung von Visual Studio .NET der neuen Eigenschaft ein [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md)-Tag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7b219-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="7b219-109">Sie sollten dann manuell ein \<value>-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="7b219-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="7b219-110">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="7b219-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b219-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b219-111">Example</span></span>  
 <span data-ttu-id="7b219-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b219-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b219-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b219-113">See Also</span></span>  
 <span data-ttu-id="7b219-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b219-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="7b219-115">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="7b219-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

