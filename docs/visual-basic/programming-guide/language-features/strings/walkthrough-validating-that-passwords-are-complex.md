---
title: Überprüfen der Komplexität von Kenn Wörtern
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 7b2d6a81f5dc88688a469b96d56a098a2b45c59f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363684"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="8fc99-102">Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fc99-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="8fc99-103">Diese Methode prüft auf einige Merkmale mit starkem Kennwort und aktualisiert einen Zeichen folgen Parameter mit Informationen darüber, welche Überprüfungen das Kennwort nicht ausführt.</span><span class="sxs-lookup"><span data-stu-id="8fc99-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="8fc99-104">Kenn Wörter können in einem sicheren System verwendet werden, um einen Benutzer zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="8fc99-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="8fc99-105">Allerdings müssen die Kenn Wörter für nicht autorisierte Benutzer schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="8fc99-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="8fc99-106">Angreifer können ein *Wörterbuch Angriffs* Programm verwenden, das alle Wörter in einem Wörterbuch (oder mehreren Wörterbüchern in verschiedenen Sprachen) durchläuft und testet, ob eines der Wörter als Kennwort eines Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8fc99-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="8fc99-107">Schwache Kenn Wörter wie "Yankees" oder "Mustang" können schnell erraten werden.</span><span class="sxs-lookup"><span data-stu-id="8fc99-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="8fc99-108">Stärkere Kenn Wörter, z. b. "? Sie ' L1N3vaFiNdMeyeP@sSWerd ! ' sind viel weniger wahrscheinlich erraten.</span><span class="sxs-lookup"><span data-stu-id="8fc99-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="8fc99-109">Ein Kenn Wort geschütztes System sollte sicherstellen, dass Benutzer sichere Kenn Wörter auswählen.</span><span class="sxs-lookup"><span data-stu-id="8fc99-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="8fc99-110">Ein sicheres Kennwort ist komplex (enthält eine Mischung aus Großbuchstaben, Kleinbuchstaben, Zahlen und Sonderzeichen) und ist kein Wort.</span><span class="sxs-lookup"><span data-stu-id="8fc99-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="8fc99-111">In diesem Beispiel wird veranschaulicht, wie die Komplexität überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="8fc99-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fc99-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fc99-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="8fc99-113">Code</span><span class="sxs-lookup"><span data-stu-id="8fc99-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="8fc99-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8fc99-114">Compile the code</span></span>  
 <span data-ttu-id="8fc99-115">Durch übergeben der Zeichenfolge, die das Kennwort enthält, wird diese Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8fc99-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="8fc99-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8fc99-116">This example requires:</span></span>  
  
- <span data-ttu-id="8fc99-117">Zugriff auf die Member des <xref:System.Text.RegularExpressions>-Namespace</span><span class="sxs-lookup"><span data-stu-id="8fc99-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="8fc99-118">Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren.</span><span class="sxs-lookup"><span data-stu-id="8fc99-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="8fc99-119">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="8fc99-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="8fc99-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8fc99-120">Security</span></span>  
 <span data-ttu-id="8fc99-121">Wenn Sie das Kennwort über ein Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="8fc99-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="8fc99-122">Weitere Informationen finden Sie unter [ASP.NET Webanwendungs Sicherheit](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8fc99-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="8fc99-123">Sie können die Genauigkeit der Funktion verbessern, `ValidatePassword` indem Sie zusätzliche Komplexitäts Überprüfungen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8fc99-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="8fc99-124">Vergleichen Sie das Kennwort und seine Teil Zeichenfolgen mit dem Namen des Benutzers, der Benutzer-ID und einem Anwendungs definierten Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="8fc99-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="8fc99-125">Behandeln Sie außerdem visuell ähnliche Zeichen als gleichwertig, wenn Sie die Vergleiche durchführen.</span><span class="sxs-lookup"><span data-stu-id="8fc99-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="8fc99-126">Behandeln Sie z. b. die Buchstaben "l" und "e" als äquivalent zu den Ziffern "1" und "3".</span><span class="sxs-lookup"><span data-stu-id="8fc99-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="8fc99-127">Wenn nur ein Großbuchstabe vorhanden ist, stellen Sie sicher, dass es sich nicht um das erste Zeichen des Kennworts handelt.</span><span class="sxs-lookup"><span data-stu-id="8fc99-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="8fc99-128">Stellen Sie sicher, dass die letzten zwei Zeichen des Kennworts Buchstaben enthalten.</span><span class="sxs-lookup"><span data-stu-id="8fc99-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="8fc99-129">Lassen Sie keine Kenn Wörter zu, bei denen alle Symbole aus der obersten Zeile der Tastatur eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8fc99-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc99-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8fc99-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="8fc99-131">[Sicherheit von ASP.NET-Webanwendungen](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8fc99-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
