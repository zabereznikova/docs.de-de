---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 904d573514bf35b773d47321b7fd3b6a86e90262
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524700"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="c7dbe-102">\<permission > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7dbe-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="c7dbe-103">Gibt eine erforderliche Berechtigung für den Member an.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7dbe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7dbe-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7dbe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7dbe-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="c7dbe-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="c7dbe-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c7dbe-108">Schließen Sie `member` in Anführungszeichen ("") ein.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c7dbe-109">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="c7dbe-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7dbe-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7dbe-110">Remarks</span></span>  
 <span data-ttu-id="c7dbe-111">Verwenden Sie das `<permission>`-Tag, um den Zugriff eines Members zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="c7dbe-112">Verwenden Sie die <xref:System.Security.PermissionSet>-Klasse, um den Zugriff auf einen Member anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="c7dbe-113">Kompilieren Sie mit [-doc](../../../visual-basic/reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7dbe-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7dbe-114">Example</span></span>  
 <span data-ttu-id="c7dbe-115">In diesem Beispiel wird das `<permission>`-Tags verwendet, um zu beschreiben, dass die <xref:System.Security.Permissions.FileIOPermission> von der `ReadFile`-Methode benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c7dbe-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="c7dbe-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7dbe-116">See also</span></span>

- [<span data-ttu-id="c7dbe-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="c7dbe-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
