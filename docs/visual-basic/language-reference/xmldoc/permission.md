---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: ae6167f3582fe22cd10d9ef7a10873d6d9bdfa06
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872551"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="e31c5-101">\<permission> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e31c5-101">\<permission> (Visual Basic)</span></span>

<span data-ttu-id="e31c5-102">Gibt eine erforderliche Berechtigung für den Member an.</span><span class="sxs-lookup"><span data-stu-id="e31c5-102">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e31c5-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="e31c5-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e31c5-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="e31c5-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="e31c5-105">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e31c5-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e31c5-106">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="e31c5-106">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="e31c5-107">Schließen Sie `member` in Anführungszeichen ("") ein.</span><span class="sxs-lookup"><span data-stu-id="e31c5-107">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="e31c5-108">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="e31c5-108">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e31c5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e31c5-109">Remarks</span></span>  

 <span data-ttu-id="e31c5-110">Verwenden Sie das- `<permission>` Tag, um den Zugriff eines Members zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="e31c5-110">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="e31c5-111">Verwenden Sie die- <xref:System.Security.PermissionSet> Klasse, um den Zugriff auf einen Member anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e31c5-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="e31c5-112">Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e31c5-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e31c5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e31c5-113">Example</span></span>  

 <span data-ttu-id="e31c5-114">In diesem Beispiel wird das- `<permission>` Tag verwendet, um zu beschreiben, dass für <xref:System.Security.Permissions.FileIOPermission> die-Methode erforderlich ist `ReadFile` .</span><span class="sxs-lookup"><span data-stu-id="e31c5-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="e31c5-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e31c5-115">See also</span></span>

- [<span data-ttu-id="e31c5-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="e31c5-116">XML Comment Tags</span></span>](index.md)
