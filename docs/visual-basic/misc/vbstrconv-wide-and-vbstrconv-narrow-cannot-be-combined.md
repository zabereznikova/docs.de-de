---
title: "Konstanten und VbStrConv.Narrow können nicht kombiniert werden | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f4f94b81654679d0181d39140230371e55ab4d92
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="9aac6-102">VbStrConv.Wide und VbStrConv.Narrow können nicht kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="9aac6-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>
<span data-ttu-id="9aac6-103">Die Anwendung versucht, die sich gegenseitig ausschließenden `VbStrConv` -Enumerationsmember `Wide` und `Narrow`zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9aac6-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9aac6-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9aac6-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="9aac6-105">Entfernen Sie entweder `VbStrConv.Wide` oder `VbStrConv.Narrow`.</span><span class="sxs-lookup"><span data-stu-id="9aac6-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aac6-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9aac6-106">See Also</span></span>  
 <span data-ttu-id="9aac6-107"><xref:System.Globalization></span><span class="sxs-lookup"><span data-stu-id="9aac6-107"><xref:System.Globalization></span></span>   
<span data-ttu-id="9aac6-108"> [NOTINBUILD VbStrConv-Enumeration](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936) </span><span class="sxs-lookup"><span data-stu-id="9aac6-108"> [NOTINBUILD VbStrConv Enumeration](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936) </span></span>  
<span data-ttu-id="9aac6-109"> [Einführung in internationale Anwendungen basierend auf .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span><span class="sxs-lookup"><span data-stu-id="9aac6-109"> [Introduction to International Applications Based on the .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span></span>
