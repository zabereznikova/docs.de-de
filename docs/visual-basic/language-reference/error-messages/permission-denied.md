---
title: Berechtigung verweigert (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: d904ee48ee187d073647b6e09af57264c8c318f6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813950"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="a7d1d-102">Berechtigung verweigert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7d1d-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="a7d1d-103">Es wurde in einem schreibgeschützten Datenträger geschrieben oder auf eine gesperrte Datei zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="a7d1d-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7d1d-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a7d1d-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="a7d1d-105">Ändern Sie das Schreibschutzattribut der Datei, um eine Datei schreibgeschützt zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a7d1d-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2.  <span data-ttu-id="a7d1d-106">Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess gesperrt hat, und warten Sie, bis die Datei zu öffnen, bis der andere Prozess freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a7d1d-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3.  <span data-ttu-id="a7d1d-107">Um die Registrierung zugreifen zu können, überprüfen Sie, dass Ihre Benutzerberechtigungen diese Art von Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="a7d1d-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d1d-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7d1d-108">See also</span></span>

- [<span data-ttu-id="a7d1d-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="a7d1d-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
