---
title: Verwenden Sie &#39; FileGetObject &#39; anstelle von &#39; FileGet &#39; Bei Verwendung von Argument vom Typ &#39; Object &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="4fa4e-102">Verwenden Sie &#39; FileGetObject &#39; anstelle von &#39; FileGet &#39; Bei Verwendung von Argument vom Typ &#39; Object &#39;</span><span class="sxs-lookup"><span data-stu-id="4fa4e-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="4fa4e-103">Die `FileGet` -Methode enthält ein Argument vom Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="4fa4e-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="4fa4e-104">`FileGetObject` sollte anstelle von `FileGet` verwendet werden, um Mehrdeutigkeiten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4fa4e-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="4fa4e-105">Beachten Sie, dass die von `My.Computer.Filesystem` bereitgestellte Funktionalität benutzerfreundlicher und leistungsfähiger als `FileGet` oder `FileGetObject`ist.</span><span class="sxs-lookup"><span data-stu-id="4fa4e-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4fa4e-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4fa4e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="4fa4e-107">Ersetzen Sie `FileGet` durch `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="4fa4e-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="4fa4e-108">Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.</span><span class="sxs-lookup"><span data-stu-id="4fa4e-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa4e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fa4e-109">See Also</span></span>  
   
 [<span data-ttu-id="4fa4e-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="4fa4e-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
