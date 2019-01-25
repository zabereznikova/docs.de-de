---
title: 'Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c0d39ecbaf9ca23c72e45b8839d268fbc38fe48e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648449"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="5297c-102">Vorgehensweise: Überprüfen Sie Dateinamen und Pfaden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5297c-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="5297c-103">In diesem Beispiel gibt eine `Boolean` Wert, der angibt, ob eine Zeichenfolge einen Dateinamen oder den Pfad darstellt.</span><span class="sxs-lookup"><span data-stu-id="5297c-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="5297c-104">Die Validierung wird überprüft, ob der Name Zeichen enthält, die vom Dateisystem nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="5297c-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5297c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5297c-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 <span data-ttu-id="5297c-106">In diesem Beispiel überprüft nicht, wenn Sie der Namen Doppelpunkte oder Verzeichnisse ohne Namen falsch platziert wurden oder die Länge des Namens vom System definierte maximale Länge überschreitet.</span><span class="sxs-lookup"><span data-stu-id="5297c-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="5297c-107">Es wird auch nicht überprüft, wenn die Anwendung die Berechtigung zum Zugriff auf die Ressource für das Dateisystem mit dem angegebenen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="5297c-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5297c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5297c-108">See also</span></span>
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="5297c-109">Überprüfen von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5297c-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
