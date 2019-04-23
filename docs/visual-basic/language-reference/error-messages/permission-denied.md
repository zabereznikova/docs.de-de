---
title: Berechtigung verweigert (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: ad75c556748bf5c0f9cef55310c4ffa7b01fd458
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318831"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="8a60e-102">Berechtigung verweigert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a60e-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="8a60e-103">Es wurde in einem schreibgeschützten Datenträger geschrieben oder auf eine gesperrte Datei zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="8a60e-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8a60e-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8a60e-104">To correct this error</span></span>  
  
1. <span data-ttu-id="8a60e-105">Ändern Sie das Schreibschutzattribut der Datei, um eine Datei schreibgeschützt zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8a60e-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="8a60e-106">Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess gesperrt hat, und warten Sie, bis die Datei zu öffnen, bis der andere Prozess freigegeben.</span><span class="sxs-lookup"><span data-stu-id="8a60e-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="8a60e-107">Um die Registrierung zugreifen zu können, überprüfen Sie, dass Ihre Benutzerberechtigungen diese Art von Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="8a60e-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a60e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a60e-108">See also</span></span>

- [<span data-ttu-id="8a60e-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="8a60e-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
