---
title: System.Convert-Methoden
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: a16839bf64d5786caa6feb557333fe93c66edc3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357373"
---
# <a name="systemconvert-methods"></a><span data-ttu-id="611cb-102">System.Convert-Methoden</span><span class="sxs-lookup"><span data-stu-id="611cb-102">System.Convert Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="611cb-103"> unterstützt die folgenden <xref:System.Convert>-Methoden nicht.</span><span class="sxs-lookup"><span data-stu-id="611cb-103"> does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="611cb-104">Versionen mit einem <xref:System.IFormatProvider>-Parameter.</span><span class="sxs-lookup"><span data-stu-id="611cb-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="611cb-105">Methoden, die Zeichen- oder Bytearrays einschließen:</span><span class="sxs-lookup"><span data-stu-id="611cb-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="611cb-106">Die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="611cb-106">The following methods:</span></span>  
  
    -   <span data-ttu-id="611cb-107">`public static <Type2> To<Type2>(<Type1> value);`. Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="611cb-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>  
  
         <span data-ttu-id="611cb-108">`Type1` und `Type2` gehören jeweils zu `sbyte`, `uint`, `ulong` oder `ushort`.</span><span class="sxs-lookup"><span data-stu-id="611cb-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="611cb-109">C#:</span><span class="sxs-lookup"><span data-stu-id="611cb-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="611cb-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="611cb-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="611cb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="611cb-111">See Also</span></span>  
 [<span data-ttu-id="611cb-112">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="611cb-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
