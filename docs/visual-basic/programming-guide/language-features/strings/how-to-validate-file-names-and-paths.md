---
title: 'Vorgehensweise: Überprüfen von Dateinamen und Pfaden'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: 3b4695dfbcaf05c73bd53af5be7a49d081eb8e47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410579"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="5db3e-102">Gewusst wie: Überprüfen von Dateinamen und Pfaden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5db3e-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="5db3e-103">In diesem Beispiel wird ein Wert zurückgegeben `Boolean` , der angibt, ob eine Zeichenfolge einen Dateinamen oder einen Pfad darstellt.</span><span class="sxs-lookup"><span data-stu-id="5db3e-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="5db3e-104">Die Validierung prüft, ob der Name Zeichen enthält, die vom Dateisystem nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="5db3e-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5db3e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5db3e-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="5db3e-106">In diesem Beispiel wird nicht überprüft, ob der Name falsch platzierte Doppelpunkte oder Verzeichnisse ohne Namen enthält oder ob die Länge des Namens die vom System definierte maximale Länge überschreitet.</span><span class="sxs-lookup"><span data-stu-id="5db3e-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="5db3e-107">Außerdem wird nicht überprüft, ob die Anwendung über die Berechtigung zum Zugreifen auf die Dateisystem Ressource mit dem angegebenen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="5db3e-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db3e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5db3e-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="5db3e-109">Überprüfen von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5db3e-109">Validating Strings in Visual Basic</span></span>](validating-strings.md)
