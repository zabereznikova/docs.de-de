---
title: '&lt;Zusammenfassung&gt; (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 42321daf092c4b637d2f75fb7f6d7e95201791ba
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017

---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="4fd8f-102">&lt;Zusammenfassung&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fd8f-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="4fd8f-103">Gibt die Zusammenfassung des Elements an.</span><span class="sxs-lookup"><span data-stu-id="4fd8f-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fd8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fd8f-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4fd8f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4fd8f-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="4fd8f-106">Eine Zusammenfassung des Objekts.</span><span class="sxs-lookup"><span data-stu-id="4fd8f-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fd8f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fd8f-107">Remarks</span></span>  
 <span data-ttu-id="4fd8f-108">Verwenden der `<summary>` Tag, um einen Typ oder einen Typmember zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4fd8f-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="4fd8f-109">Verwendung [ \<Hinweise >](../../../visual-basic/language-reference/xmldoc/remarks.md) zusätzliche Informationen zur eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="4fd8f-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="4fd8f-110">Der Text für die `<summary>` -Tag ist die einzige Quelle von Informationen über den Typ in IntelliSense und wird auch im Objektkatalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4fd8f-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="4fd8f-111">Informationen über den Objektkatalog finden Sie unter [Anzeigen der Struktur des Codes](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="4fd8f-111">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="4fd8f-112">Kompilieren Sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) Dokumentationskommentare zu einer Datei.</span><span class="sxs-lookup"><span data-stu-id="4fd8f-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fd8f-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4fd8f-113">Example</span></span>  
 <span data-ttu-id="4fd8f-114">Dieses Beispiel verwendet die `<summary>` Tag beschreiben die `ResetCounter` Methode und `Counter` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4fd8f-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 <span data-ttu-id="4fd8f-115">[!code-vb[VbVbcnXmlDocComments&#1;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4fd8f-115">[!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd8f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fd8f-116">See Also</span></span>  
 [<span data-ttu-id="4fd8f-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="4fd8f-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
