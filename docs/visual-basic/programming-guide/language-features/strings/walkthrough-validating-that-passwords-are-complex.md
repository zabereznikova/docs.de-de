---
title: Überprüfen die Komplexität der Kennwörter (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 829d6485acdca22fbf10160c734e5c7f931dd855
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824935"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="81c81-102">Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81c81-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="81c81-103">Diese Methode überprüft, ob eine sichere Kennworteigenschaften gewählt und aktualisiert einen Zeichenfolgenparameter mit Informationen, die über die das Kennwort überprüft schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="81c81-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="81c81-104">Kennwörter können in einem sicheren System zum Autorisieren eines Benutzers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81c81-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="81c81-105">Allerdings müssen die Kennwörter für nicht autorisierte Benutzer schwierig zu erraten sein.</span><span class="sxs-lookup"><span data-stu-id="81c81-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="81c81-106">Angreifer können einen *Wörterbuchangriff* Programm, das alle der Wörter in einem Wörterbuch (oder mehreren Wörterbüchern in verschiedenen Sprachen) durchlaufen und testet, ob alle der Wörter als das Kennwort eines Benutzers arbeiten.</span><span class="sxs-lookup"><span data-stu-id="81c81-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="81c81-107">Schwache Kennwörter wie "Yankees" oder "Mustang" können schnell ausspioniert werden.</span><span class="sxs-lookup"><span data-stu-id="81c81-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="81c81-108">Sicherere Kennwörter, z. B. "? Sie "L1N3vaFiNdMeyeP@sSWerd!", sehr viel weniger wahrscheinlich erraten werden.</span><span class="sxs-lookup"><span data-stu-id="81c81-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="81c81-109">Ein Kennwort geschützt sind und sorgen dafür, dass Benutzer sichere Kennwörter wählen.</span><span class="sxs-lookup"><span data-stu-id="81c81-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="81c81-110">Ein sicheres Kennwort ist komplex (enthält eine Mischung aus Großbuchstaben, Kleinbuchstaben, numerische und Sonderzeichen), und es ist kein Word.</span><span class="sxs-lookup"><span data-stu-id="81c81-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="81c81-111">Dieses Beispiel zeigt, wie Sie Komplexität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="81c81-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81c81-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81c81-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="81c81-113">Code</span><span class="sxs-lookup"><span data-stu-id="81c81-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81c81-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="81c81-114">Compiling the Code</span></span>  
 <span data-ttu-id="81c81-115">Rufen Sie diese Methode übergeben Sie die Zeichenfolge, die das Kennwort enthält, ein.</span><span class="sxs-lookup"><span data-stu-id="81c81-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="81c81-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="81c81-116">This example requires:</span></span>  
  
-   <span data-ttu-id="81c81-117">Zugriff auf die Member des <xref:System.Text.RegularExpressions>-Namespace</span><span class="sxs-lookup"><span data-stu-id="81c81-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="81c81-118">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="81c81-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="81c81-119">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="81c81-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="81c81-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="81c81-120">Security</span></span>  
 <span data-ttu-id="81c81-121">Wenn Sie das Kennwort über ein Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="81c81-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="81c81-122">Weitere Informationen finden Sie unter [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="81c81-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="81c81-123">Sie können die Genauigkeit der verbessern die `ValidatePassword` Funktion durch Hinzufügen zusätzlicher komplexitätsüberprüfungen:</span><span class="sxs-lookup"><span data-stu-id="81c81-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="81c81-124">Vergleichen Sie das Kennwort und die Teilzeichenfolgen vor den Namen des Benutzers, Benutzer-ID und ein Wörterbuch anwendungsdefinierte.</span><span class="sxs-lookup"><span data-stu-id="81c81-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="81c81-125">Darüber hinaus visuell ähnliche Zeichen als gleichwertig behandelt, bei der die Vergleiche ausführen.</span><span class="sxs-lookup"><span data-stu-id="81c81-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="81c81-126">Behandeln Sie z. B. den Buchstaben "l" und "e" als Entsprechung zu die Ziffern "1" und "3".</span><span class="sxs-lookup"><span data-stu-id="81c81-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="81c81-127">Ist nur ein Großbuchstabe, stellen Sie sicher, dass es sich nicht um das Kennwort des ersten Zeichens ist.</span><span class="sxs-lookup"><span data-stu-id="81c81-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="81c81-128">Stellen Sie sicher, dass die letzten beiden Zeichen des Kennworts Buchstaben sind.</span><span class="sxs-lookup"><span data-stu-id="81c81-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="81c81-129">Lassen Sie nicht die Kennwörter, die in denen alle Symbole, die von der Tastatur die oberste Zeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="81c81-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c81-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81c81-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="81c81-131">[Sicherheit von ASP.NET-Webanwendungen](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="81c81-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
