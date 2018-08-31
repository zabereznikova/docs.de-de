---
title: '&lt;Berechtigung&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: bcec5d968f5d0c5400c28e772df151b164888a47
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257434"
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="d9169-102">&lt;Berechtigung&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9169-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="d9169-103">Gibt eine erforderliche Berechtigung für das Element an.</span><span class="sxs-lookup"><span data-stu-id="d9169-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9169-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9169-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9169-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9169-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="d9169-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9169-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="d9169-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="d9169-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="d9169-108">Schließen Sie `member` in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="d9169-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d9169-109">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="d9169-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9169-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9169-110">Remarks</span></span>  
 <span data-ttu-id="d9169-111">Verwenden der `<permission>` Tag, um den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="d9169-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="d9169-112">Verwenden der <xref:System.Security.PermissionSet> Klasse, um den Zugriff auf ein Element anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d9169-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="d9169-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="d9169-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9169-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9169-114">Example</span></span>  
 <span data-ttu-id="d9169-115">Dieses Beispiel verwendet die `<permission>` Tag beschrieben, dass die <xref:System.Security.Permissions.FileIOPermission> erforderlich ist der `ReadFile` Methode.</span><span class="sxs-lookup"><span data-stu-id="d9169-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d9169-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9169-116">See Also</span></span>  
 [<span data-ttu-id="d9169-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="d9169-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
