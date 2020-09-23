---
title: Verwenden Sie "FileGetObject" statt "FileGet", wenn ein Argument des Typs "Object" verwendet wird
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059404"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="887b5-102">Verwenden Sie "FileGetObject" statt "FileGet", wenn ein Argument des Typs "Object" verwendet wird</span><span class="sxs-lookup"><span data-stu-id="887b5-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>

<span data-ttu-id="887b5-103">Die `FileGet` -Methode enthält ein Argument vom Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="887b5-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="887b5-104">`FileGetObject` sollte anstelle von `FileGet` verwendet werden, um Mehrdeutigkeiten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="887b5-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="887b5-105">Beachten Sie, dass die von `My.Computer.Filesystem` bereitgestellte Funktionalität benutzerfreundlicher und leistungsfähiger als `FileGet` oder `FileGetObject`ist.</span><span class="sxs-lookup"><span data-stu-id="887b5-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="887b5-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="887b5-106">To correct this error</span></span>  
  
1. <span data-ttu-id="887b5-107">Ersetzen Sie `FileGet` durch `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="887b5-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="887b5-108">Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.</span><span class="sxs-lookup"><span data-stu-id="887b5-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887b5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="887b5-109">See also</span></span>

- [<span data-ttu-id="887b5-110">My. Computer. File System</span><span class="sxs-lookup"><span data-stu-id="887b5-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
