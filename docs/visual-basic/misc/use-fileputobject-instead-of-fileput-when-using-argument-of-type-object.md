---
title: Verwendung &#39;FilePutObject&#39; anstelle von &#39;FilePut&#39; Wenn ein Argument des Typs verwendet &#39;Objekt&#39;
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 529352d98c175981c20861205ce04c8a2ebcdca9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="48ec5-102">Verwendung &#39;FilePutObject&#39; anstelle von &#39;FilePut&#39; Wenn ein Argument des Typs verwendet &#39;Objekt&#39;</span><span class="sxs-lookup"><span data-stu-id="48ec5-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="48ec5-103">Die `FilePut` -Methode enthält ein Argument des Typs `Object`.</span><span class="sxs-lookup"><span data-stu-id="48ec5-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="48ec5-104">`FilePutObject` sollte anstelle von `FilePut` verwendet werden, um Mehrdeutigkeiten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="48ec5-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48ec5-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="48ec5-105">To correct this error</span></span>  
  
-   <span data-ttu-id="48ec5-106">Ersetzen Sie `FilePut` durch `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="48ec5-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="48ec5-107">Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.</span><span class="sxs-lookup"><span data-stu-id="48ec5-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="48ec5-108">Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="48ec5-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ec5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48ec5-109">See Also</span></span>  
   
 [<span data-ttu-id="48ec5-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="48ec5-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="48ec5-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="48ec5-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
