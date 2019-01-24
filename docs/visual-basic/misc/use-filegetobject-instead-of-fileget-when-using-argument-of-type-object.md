---
title: Verwenden Sie 'FileGetObject' statt 'FileGet', wenn ein Argument des Typs 'Object' verwendet wird
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 60eaabc686070aced908116728f06d4e82b5cecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723393"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="31eaf-102">Verwenden Sie 'FileGetObject' statt 'FileGet', wenn ein Argument des Typs 'Object' verwendet wird</span><span class="sxs-lookup"><span data-stu-id="31eaf-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>
<span data-ttu-id="31eaf-103">Die `FileGet` -Methode enthält ein Argument vom Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="31eaf-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="31eaf-104">`FileGetObject` sollte anstelle von `FileGet` verwendet werden, um Mehrdeutigkeiten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="31eaf-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="31eaf-105">Beachten Sie, dass die von `My.Computer.Filesystem` bereitgestellte Funktionalität benutzerfreundlicher und leistungsfähiger als `FileGet` oder `FileGetObject`ist.</span><span class="sxs-lookup"><span data-stu-id="31eaf-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="31eaf-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="31eaf-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="31eaf-107">Ersetzen Sie `FileGet` durch `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="31eaf-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="31eaf-108">Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.</span><span class="sxs-lookup"><span data-stu-id="31eaf-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31eaf-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31eaf-109">See also</span></span>

- [<span data-ttu-id="31eaf-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="31eaf-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
