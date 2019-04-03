---
title: Fehler beim Laden der DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816901"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="16830-102">Fehler beim Laden der DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16830-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="16830-103">Eine Dynamic Link Library (DLL) ist eine Bibliothek, die im angegebenen die `Lib` -Klausel einer `Declare` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="16830-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="16830-104">Möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="16830-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="16830-105">Die Datei ist keine ausführbare DLL-Datei.</span><span class="sxs-lookup"><span data-stu-id="16830-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="16830-106">Die Datei ist nicht Microsoft Windows DLL.</span><span class="sxs-lookup"><span data-stu-id="16830-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="16830-107">Die DLL verweist auf eine andere DLL, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="16830-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="16830-108">Die DLL oder dem referenzierten DLL ist nicht in einem Verzeichnis im Pfad angegeben.</span><span class="sxs-lookup"><span data-stu-id="16830-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16830-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="16830-109">To correct this error</span></span>  
  
-   <span data-ttu-id="16830-110">Wenn die Datei eine Source-Text-Datei und daher nicht die ausführbare DLL ist, muss Sie kompiliert und mit einem ausführbaren DLL-Formular verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="16830-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="16830-111">Wenn die Datei nicht um eine Microsoft Windows-DLL ist, rufen Sie die entsprechende Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="16830-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="16830-112">Wenn die DLL eine andere DLL, die nicht vorhanden ist verweist, erhalten Sie die referenzierte DLL und macht sie verfügbar.</span><span class="sxs-lookup"><span data-stu-id="16830-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="16830-113">Wenn die DLL oder dem referenzierten DLL nicht in einem Verzeichnis, das durch den Pfad angegeben ist, verschieben Sie die DLL, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="16830-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16830-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16830-114">See also</span></span>

- [<span data-ttu-id="16830-115">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16830-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
