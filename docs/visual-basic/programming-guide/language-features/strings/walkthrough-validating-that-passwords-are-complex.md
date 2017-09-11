---
title: "Überprüfen der Komplexität der Kennwörter (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8d636c1e43de6a108cdc217cb21aaf7689e175f7
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="46cb2-102">Exemplarische Vorgehensweise: Überprüfen der Komplexität von Kennwörtern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46cb2-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="46cb2-103">Diese Methode überprüft, ob einige Merkmale sichere Kennwörter und aktualisiert einen Zeichenfolgenparameter mit Informationen darüber, welche das Kennwort überprüft ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="46cb2-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="46cb2-104">Kennwörter können in einem sicheren System zum Autorisieren eines Benutzers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46cb2-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="46cb2-105">Allerdings müssen die Kennwörter für nicht autorisierte Benutzer schwierig zu erraten sein.</span><span class="sxs-lookup"><span data-stu-id="46cb2-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="46cb2-106">Angreifer können einen *Wörterbuchangriff* Programm an, die alle Wörter im Wörterbuch (oder mehreren Wörterbüchern in verschiedenen Sprachen) durchlaufen und überprüft, ob eines der Wörter als das Kennwort eines Benutzers arbeiten.</span><span class="sxs-lookup"><span data-stu-id="46cb2-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="46cb2-107">Unsichere Kennwörter, z. B. "Yankees" oder "Mustang", können schnell erraten.</span><span class="sxs-lookup"><span data-stu-id="46cb2-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="46cb2-108">Sicherere Kennwörter, z. B. "? Sie "L1N3vaFiNdMeyeP@sSWerd!", sind viel zu erraten.</span><span class="sxs-lookup"><span data-stu-id="46cb2-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="46cb2-109">Ein kennwortgeschütztes System sollten sicherstellen, dass Benutzer sichere Kennwörter auswählen.</span><span class="sxs-lookup"><span data-stu-id="46cb2-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="46cb2-110">Ein sicheres Kennwort ist komplex (mit einer Mischung aus Großbuchstaben, Kleinbuchstaben, numerischen und Sonderzeichen) und ein Wort ist.</span><span class="sxs-lookup"><span data-stu-id="46cb2-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="46cb2-111">In diesem Beispiel wird veranschaulicht, wie Komplexität überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="46cb2-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46cb2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46cb2-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="46cb2-113">Code</span><span class="sxs-lookup"><span data-stu-id="46cb2-113">Code</span></span>  
 <span data-ttu-id="46cb2-114">[!code-vb[VbVbcnRegEx&#1;](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="46cb2-114">[!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46cb2-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="46cb2-115">Compiling the Code</span></span>  
 <span data-ttu-id="46cb2-116">Rufen Sie diese Methode auf, übergeben Sie die Zeichenfolge, die dieses Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="46cb2-116">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="46cb2-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="46cb2-117">This example requires:</span></span>  
  
-   <span data-ttu-id="46cb2-118">Zugriff auf die Mitglieder der <xref:System.Text.RegularExpressions>Namespace.</xref:System.Text.RegularExpressions></span><span class="sxs-lookup"><span data-stu-id="46cb2-118">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="46cb2-119">Hinzufügen einer `Imports` -Anweisung, falls Sie nicht vollständig in Ihrem Code Membernamen enthält.</span><span class="sxs-lookup"><span data-stu-id="46cb2-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="46cb2-120">Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="46cb2-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="46cb2-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="46cb2-121">Security</span></span>  
 <span data-ttu-id="46cb2-122">Wenn Sie das Kennwort über ein Netzwerk verschieben, müssen Sie eine sichere Methode zum Übertragen von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="46cb2-122">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="46cb2-123">Weitere Informationen finden Sie unter [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="46cb2-123">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="46cb2-124">Sie können die Genauigkeit der verbessern die `ValidatePassword` Funktion durch Hinzufügen von zusätzlichen Komplexität überprüft:</span><span class="sxs-lookup"><span data-stu-id="46cb2-124">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="46cb2-125">Vergleichen Sie das Kennwort und seine Teilzeichenfolgen mit den Namen des Benutzers, Benutzer-ID und einem anwendungsdefinierten Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="46cb2-125">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="46cb2-126">Darüber hinaus behandeln Sie sieht ähnlich aus wie Zeichen als gleichwertig, wenn Sie die Vergleiche ausführen.</span><span class="sxs-lookup"><span data-stu-id="46cb2-126">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="46cb2-127">Behandeln Sie z. B. den Buchstaben "l" und "e" als gleichwertig mit der Zahlen "1" und "3".</span><span class="sxs-lookup"><span data-stu-id="46cb2-127">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="46cb2-128">Wenn nur ein Großbuchstabe vorhanden ist, stellen Sie sicher, dass sie nicht das Kennwort des ersten Zeichens.</span><span class="sxs-lookup"><span data-stu-id="46cb2-128">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="46cb2-129">Stellen Sie sicher, dass die letzten beiden Zeichen des Kennworts Buchstaben sind.</span><span class="sxs-lookup"><span data-stu-id="46cb2-129">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="46cb2-130">Erlauben Sie keine Kennwörter in denen alle Symbole aus der Tastatur oberste Zeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="46cb2-130">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46cb2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46cb2-131">See Also</span></span>  
 <span data-ttu-id="46cb2-132"><xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex></span><span class="sxs-lookup"><span data-stu-id="46cb2-132"><xref:System.Text.RegularExpressions.Regex></span></span>   
<span data-ttu-id="46cb2-133"> [Sicherheit von ASP.NET-Webanwendungen](https://msdn.microsoft.com/library/330a99hc)</span><span class="sxs-lookup"><span data-stu-id="46cb2-133"> [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc)</span></span>
