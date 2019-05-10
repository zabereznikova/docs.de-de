---
title: Verwenden Sie 'FilePutObject' statt 'FilePut', wenn ein Argument des Typs 'Object' verwendet wird.
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: bf1f50d0d8eb9b0b8518075b0e48f40645a02a25
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913216"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="601d4-102">Verwenden Sie 'FilePutObject' statt 'FilePut', wenn ein Argument des Typs 'Object' verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="601d4-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="601d4-103">Die `FilePut` -Methode enthält ein Argument vom Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="601d4-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="601d4-104">`FilePutObject` sollte anstelle von `FilePut` verwendet werden, um Mehrdeutigkeiten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="601d4-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="601d4-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="601d4-105">To correct this error</span></span>  
  
- <span data-ttu-id="601d4-106">Ersetzen Sie `FilePut` durch `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="601d4-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="601d4-107">Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.</span><span class="sxs-lookup"><span data-stu-id="601d4-107">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="601d4-108">Verwenden Sie die im `My.Computer.FileSystem` -Objekt verfügbare Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="601d4-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="601d4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="601d4-109">See also</span></span>

- [<span data-ttu-id="601d4-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="601d4-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="601d4-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="601d4-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
