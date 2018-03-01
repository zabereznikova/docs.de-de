---
title: Fehler beim Laden der DLL (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc557dcc6709178b6519adb56f31debcbd1d1c39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="0e6b5-102">Fehler beim Laden der DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e6b5-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="0e6b5-103">Eine Dynamic Link Library (DLL) ist eine Bibliothek, die im angegebenen der `Lib` -Klausel eine `Declare` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="0e6b5-104">Mögliche Ursachen für diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0e6b5-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="0e6b5-105">Die Datei ist keine ausführbare DLL-Datei.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="0e6b5-106">Die Datei ist nicht Microsoft Windows DLL.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="0e6b5-107">Die DLL verweist auf eine andere DLL, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="0e6b5-108">Die DLL oder die referenzierten DLL ist nicht in einem Verzeichnis im Pfad angegeben.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0e6b5-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0e6b5-109">To correct this error</span></span>  
  
-   <span data-ttu-id="0e6b5-110">Wenn die Datei eine Textdatei auf dem Quell- und daher nicht die ausführbare DLL ist, müssen Sie kompiliert und zu einem Formular ausführbare DLL verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="0e6b5-111">Wenn die Datei nicht Microsoft Windows DLL ist, erhalten Sie Microsoft Windows-äquivalent.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="0e6b5-112">Wenn die DLL auf eine andere DLL, die nicht vorhanden ist verweist, erhalten Sie referenzierte DLL und machen Sie verfügbar zu.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="0e6b5-113">Wenn die DLL oder die referenzierten DLL nicht in einem Verzeichnis mit dem Pfad angegeben ist, verschieben Sie die DLL in ein Verzeichnis auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0e6b5-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6b5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e6b5-114">See Also</span></span>  
 [<span data-ttu-id="0e6b5-115">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0e6b5-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
