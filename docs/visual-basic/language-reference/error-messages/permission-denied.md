---
title: Berechtigung verweigert
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: 410301a1e99040fc617ab1bf1e851329ab3072d2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347005"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="37c47-102">Berechtigung verweigert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37c47-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="37c47-103">Es wurde versucht, auf einen schreibgeschützten Datenträger zu schreiben oder auf eine gesperrte Datei zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="37c47-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="37c47-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="37c47-104">To correct this error</span></span>  
  
1. <span data-ttu-id="37c47-105">Um eine schreibgeschützte Datei zu öffnen, ändern Sie das Write-Protection-Attribut der Datei.</span><span class="sxs-lookup"><span data-stu-id="37c47-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="37c47-106">Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess gesperrt wurde, und warten Sie, bis die Datei vom anderen Prozess freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="37c47-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="37c47-107">Wenn Sie auf die Registrierung zugreifen möchten, überprüfen Sie, ob die Benutzerberechtigungen diese Art von Registrierungs Zugriff einschließen.</span><span class="sxs-lookup"><span data-stu-id="37c47-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37c47-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37c47-108">See also</span></span>

- [<span data-ttu-id="37c47-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="37c47-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
