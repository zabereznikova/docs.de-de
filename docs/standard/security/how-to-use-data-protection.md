---
title: 'Vorgehensweise: Verwenden des Datenschutzes'
description: Erfahren Sie, wie Sie Datenschutz durchzugreifen auf die Datenschutz-API (Data Protection API, DPAPI) in .NET verwenden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: c7f88105727dfd33c87a815054aa317ac2052e83
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598592"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="82b6a-103">Vorgehensweise: Verwenden des Datenschutzes</span><span class="sxs-lookup"><span data-stu-id="82b6a-103">How to: Use Data Protection</span></span>
<span data-ttu-id="82b6a-104">.NET Framework bietet Zugriff auf die Datenschutz-API, die es Ihnen ermöglicht, Daten mithilfe von Informationen vom aktuellen Benutzerkonto oder Computer zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="82b6a-104">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="82b6a-105">Wenn Sie die Datenschutz-API verwenden, umgehen Sie die schwierige Aufgabe, einen kryptografischen Schlüssel explizit zu generieren und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="82b6a-105">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="82b6a-106">Verwenden Sie die <xref:System.Security.Cryptography.ProtectedMemory>-Klasse, um ein Array aus In-Memory-Bytes zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="82b6a-106">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="82b6a-107">Diese Funktionalität ist ab Microsoft Windows XP verfügbar.</span><span class="sxs-lookup"><span data-stu-id="82b6a-107">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="82b6a-108">Sie können angeben, dass der durch den aktuellen Prozess verschlüsselte Speicher nur durch den aktuellen Prozess, durch alle Prozesse oder von demselben Benutzerkontext entschlüsselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="82b6a-108">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="82b6a-109">In der <xref:System.Security.Cryptography.MemoryProtectionScope>-Enumeration finden Sie eine ausführliche Beschreibung der <xref:System.Security.Cryptography.ProtectedMemory>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="82b6a-109">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="82b6a-110">Verwenden Sie die <xref:System.Security.Cryptography.ProtectedData>-Klasse, um eine Kopie eines Bytearrays zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="82b6a-110">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="82b6a-111">Diese Funktionalität ist ab Microsoft Windows 2000 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="82b6a-111">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="82b6a-112">Sie können angeben, dass Daten, die über das aktuelle Benutzerkonto verschlüsselt wurden, nur über dasselbe Benutzerkonto oder über jedes Konto auf dem Computer entschlüsselt werden können.</span><span class="sxs-lookup"><span data-stu-id="82b6a-112">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="82b6a-113">In der <xref:System.Security.Cryptography.DataProtectionScope>-Enumeration finden Sie eine ausführliche Beschreibung der <xref:System.Security.Cryptography.ProtectedData>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="82b6a-113">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="82b6a-114">So verschlüsseln Sie im Arbeitsspeicher befindliche Daten mithilfe von Datenschutz</span><span class="sxs-lookup"><span data-stu-id="82b6a-114">To encrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="82b6a-115">Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A>-Methode auf, wobei Sie ein Array zu verschlüsselnder Bytes, die Entropie und den Speicherschutzbereich übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b6a-115">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="82b6a-116">So entschlüsseln Sie im Arbeitsspeicher befindliche Daten mithilfe von Datenschutz</span><span class="sxs-lookup"><span data-stu-id="82b6a-116">To decrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="82b6a-117">Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A>-Methode auf, wobei Sie ein Array zu entschlüsselnder Bytes und den Speicherschutzbereich übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b6a-117">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="82b6a-118">So verschlüsseln Sie Daten in eine Datei oder einen Stream mithilfe von Datenschutz</span><span class="sxs-lookup"><span data-stu-id="82b6a-118">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="82b6a-119">Erstellen Sie eine zufällige Entropie.</span><span class="sxs-lookup"><span data-stu-id="82b6a-119">Create random entropy.</span></span>  
  
2. <span data-ttu-id="82b6a-120">Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedData.Protect%2A>-Methode auf, wobei Sie ein Array zu verschlüsselnder Bytes, die Entropie und den Datenschutzbereich übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b6a-120">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="82b6a-121">Schreiben Sie die verschlüsselten Daten in eine Datei oder einen Stream.</span><span class="sxs-lookup"><span data-stu-id="82b6a-121">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="82b6a-122">So entschlüsseln Sie Daten aus einer Datei oder einem Stream mithilfe von Datenschutz</span><span class="sxs-lookup"><span data-stu-id="82b6a-122">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="82b6a-123">Lesen Sie die verschlüsselten Daten aus einer Datei oder einem Stream.</span><span class="sxs-lookup"><span data-stu-id="82b6a-123">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="82b6a-124">Rufen Sie die statische <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A>-Methode auf, wobei Sie ein Array zu entschlüsselnder Bytes und den Datenschutzbereich übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b6a-124">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b6a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82b6a-125">Example</span></span>  
 <span data-ttu-id="82b6a-126">Im folgenden Codebeispiel werden zwei Arten von Verschlüsselung und Entschlüsselung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="82b6a-126">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="82b6a-127">Im Codebeispiel wird zunächst ein im Arbeitsspeicher befindliches Array aus Bytes verschlüsselt und anschließend entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="82b6a-127">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="82b6a-128">Danach wird eine Kopie eines Bytearrays verschlüsselt, wird diese Kopie in einer Datei gespeichert, werden die Daten aus der Datei zurückgeladen und werden die Daten entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="82b6a-128">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="82b6a-129">Im Beispiel werden die ursprünglichen Daten, die verschlüsselten Daten und die entschlüsselten Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82b6a-129">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82b6a-130">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="82b6a-130">Compiling the Code</span></span>  
  
- <span data-ttu-id="82b6a-131">Fügen Sie einen Verweis auf `System.Security.dll` ein.</span><span class="sxs-lookup"><span data-stu-id="82b6a-131">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="82b6a-132">Fügen Sie die Namespaces <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> und <xref:System.Text> ein.</span><span class="sxs-lookup"><span data-stu-id="82b6a-132">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b6a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82b6a-133">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
