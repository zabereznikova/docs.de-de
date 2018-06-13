---
title: Überprüfen die Kennwörter Komplexität (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: acfc8ab958c8671ed7f1afd245d24a43ca12be29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650282"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="f8911-102">Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8911-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="f8911-103">Diese Methode auf einige Eigenschaften sicheres Kennwort überprüft und aktualisiert einen Zeichenfolgenparameter mit Informationen darüber, welche das Kennwort überprüft ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="f8911-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="f8911-104">Kennwörter können in einem sicheren System zum Autorisieren eines Benutzers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8911-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="f8911-105">Allerdings müssen die Kennwörter für nicht autorisierte Benutzer zu erraten schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="f8911-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="f8911-106">Angreifer können einen *Wörterbuchangriff* Programm an, die alle Wörter in einem Wörterbuch (oder mehrere Wörterbücher in verschiedenen Sprachen) durchläuft und testet, ob eines der Wörter als das Kennwort eines Benutzers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8911-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="f8911-107">Unsichere Kennwörter, z. B. "Yankees" oder "Mustang" können schnell ausspioniert werden.</span><span class="sxs-lookup"><span data-stu-id="f8911-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="f8911-108">Sicherer Kennwörter, z. B. "? Sie "L1N3vaFiNdMeyeP@sSWerd!", sind sehr viel seltener zu erraten werden.</span><span class="sxs-lookup"><span data-stu-id="f8911-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="f8911-109">Ein System kennwortgeschützte sollten sicherstellen, dass Benutzer sichere Kennwörter auswählen.</span><span class="sxs-lookup"><span data-stu-id="f8911-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="f8911-110">Ein sicheres Kennwort ist komplex (mit einer Mischung aus Großbuchstaben, Kleinbuchstaben, numerische und Sonderzeichen), ist es sich nicht um ein Wort.</span><span class="sxs-lookup"><span data-stu-id="f8911-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="f8911-111">In diesem Beispiel wird veranschaulicht, wie Komplexität überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="f8911-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8911-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8911-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="f8911-113">Code</span><span class="sxs-lookup"><span data-stu-id="f8911-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8911-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f8911-114">Compiling the Code</span></span>  
 <span data-ttu-id="f8911-115">Rufen Sie diese Methode, durch die Zeichenfolge, die das Kennwort enthält, zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f8911-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="f8911-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f8911-116">This example requires:</span></span>  
  
-   <span data-ttu-id="f8911-117">Zugriff auf die Member des <xref:System.Text.RegularExpressions>-Namespace</span><span class="sxs-lookup"><span data-stu-id="f8911-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="f8911-118">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="f8911-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="f8911-119">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="f8911-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="f8911-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f8911-120">Security</span></span>  
 <span data-ttu-id="f8911-121">Wenn Sie das Kennwort über das Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8911-121">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="f8911-122">Weitere Informationen finden Sie unter [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="f8911-122">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="f8911-123">Sie können die Genauigkeit der verbessern die `ValidatePassword` Funktion durch Hinzufügen von zusätzlichen komplexitätsüberprüfungen:</span><span class="sxs-lookup"><span data-stu-id="f8911-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="f8911-124">Vergleichen Sie das Kennwort und seine Teilzeichenfolgen anhand des Benutzernamens, Benutzer-ID und ein Wörterbuch anwendungsdefinierte.</span><span class="sxs-lookup"><span data-stu-id="f8911-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="f8911-125">Darüber hinaus behandeln Sie visuell ähnliche Zeichen als gleichwertig, wenn die Vergleiche ausführen.</span><span class="sxs-lookup"><span data-stu-id="f8911-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="f8911-126">Behandeln Sie z. B. den Buchstaben "l" und "e" als gleichwertig mit der Zahlen "1" und "3".</span><span class="sxs-lookup"><span data-stu-id="f8911-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="f8911-127">Ist nur ein Großbuchstabe, stellen Sie sicher, dass es sich nicht um das Kennwort des ersten Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="f8911-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="f8911-128">Stellen Sie sicher, dass die letzten beiden Zeichen des Kennworts Buchstaben sind.</span><span class="sxs-lookup"><span data-stu-id="f8911-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="f8911-129">Gestatten Sie keine Kennwörter in denen alle Symbole aus oberste Zeile die Tastatur eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f8911-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8911-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8911-130">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex>  
 [<span data-ttu-id="f8911-131">Sicherheit von ASP.NET-Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="f8911-131">ASP.NET Web Application Security</span></span>](https://msdn.microsoft.com/library/330a99hc)
