---
title: 'Vorgehensweise: Zugreifen auf Hardwaregeräte zur Verschlüsselung'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
ms.openlocfilehash: 7cd3aab80a8388c1d4ce08e4ae94aae84cfff239
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557137"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="d011b-102">Vorgehensweise: Zugreifen auf Hardwaregeräte zur Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="d011b-102">How to: Access Hardware Encryption Devices</span></span>

> [!NOTE]
> <span data-ttu-id="d011b-103">Dieser Artikel bezieht sich auf Windows.</span><span class="sxs-lookup"><span data-stu-id="d011b-103">This article applies to Windows.</span></span>

<span data-ttu-id="d011b-104">Mit der <xref:System.Security.Cryptography.CspParameters>-Klasse können Sie auf Verschlüsselungsgeräte zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d011b-104">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="d011b-105">Beispielsweise können Sie diese Klasse dazu verwenden, Ihre Anwendung auf eine Smartcard, einen hardwaremäßigen Zufallszahlengenerator oder eine Hardwareimplementierung eines bestimmten kryptografischen Algorithmus abzustimmen.</span><span class="sxs-lookup"><span data-stu-id="d011b-105">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  

<span data-ttu-id="d011b-106">Die <xref:System.Security.Cryptography.CspParameters>-Klasse erstellt einen Kryptografiedienstanbieter (Cryptographic Service Provider, CSP), der auf ein ordnungsgemäß installiertes Verschlüsselungsgerät zugreift.</span><span class="sxs-lookup"><span data-stu-id="d011b-106">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="d011b-107">Sie können die Verfügbarkeit eines CSP überprüfen, indem Sie sich mit dem Registrierungs-Editor (Regedit.exe) den folgenden Registrierungsschlüssel ansehen: HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="d011b-107">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="d011b-108">So signieren Sie Daten mit einer Schlüsselkarte</span><span class="sxs-lookup"><span data-stu-id="d011b-108">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="d011b-109">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.CspParameters>-Klasse, wobei Sie den ganzzahligen Anbietertyp sowie den Anbieternamen an den Konstruktor übergeben</span><span class="sxs-lookup"><span data-stu-id="d011b-109">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="d011b-110">Übergeben Sie die entsprechenden Flags an die <xref:System.Security.Cryptography.CspParameters.Flags%2A>-Eigenschaft des neu erstellten <xref:System.Security.Cryptography.CspParameters>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="d011b-110">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="d011b-111">Übergeben Sie z. B. das <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>-Flag.</span><span class="sxs-lookup"><span data-stu-id="d011b-111">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="d011b-112">Erstellen Sie eine neue Instanz einer <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Klasse (beispielsweise die <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse), wobei Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="d011b-112">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="d011b-113">Signieren Sie Ihre Daten mit einer der `Sign`-Methoden, und überprüfen Sie Ihre Daten mit einer der `Verify`-Methoden.</span><span class="sxs-lookup"><span data-stu-id="d011b-113">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="d011b-114">So generieren Sie eine Zufallszahl mit einem hardwaremäßigen Zufallszahlengenerator </span><span class="sxs-lookup"><span data-stu-id="d011b-114">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="d011b-115">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.CspParameters>-Klasse, wobei Sie den ganzzahligen Anbietertyp sowie den Anbieternamen an den Konstruktor übergeben</span><span class="sxs-lookup"><span data-stu-id="d011b-115">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="d011b-116">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.RNGCryptoServiceProvider>-Klasse, wobei Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="d011b-116">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="d011b-117">Erstellen Sie mit der <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A>-Methode oder der <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>-Methode einen zufälligen Wert.</span><span class="sxs-lookup"><span data-stu-id="d011b-117">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d011b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d011b-118">Example</span></span>

<span data-ttu-id="d011b-119">Im folgenden Codebeispiel wird veranschaulicht, wie Daten mit einer Smartcard signiert werden.</span><span class="sxs-lookup"><span data-stu-id="d011b-119">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="d011b-120">Im Codebeispiel wird ein <xref:System.Security.Cryptography.CspParameters>-Objekt erstellt, das eine Smartcard verfügbar macht, und anschließend wird mit dem CSP ein <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekt initialisiert.</span><span class="sxs-lookup"><span data-stu-id="d011b-120">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="d011b-121">Danach werden im Codebeispiel einige Daten signiert und überprüft.</span><span class="sxs-lookup"><span data-stu-id="d011b-121">The code example then signs and verifies some data.</span></span>  

<span data-ttu-id="d011b-122">Aufgrund von Konnektivitätsproblemen mit SHA1 empfehlen wir SHA256 oder eine bessere.</span><span class="sxs-lookup"><span data-stu-id="d011b-122">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>
  
[!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
[!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
[!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d011b-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d011b-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="d011b-124">Fügen Sie die Namespaces <xref:System> und <xref:System.Security.Cryptography> ein.</span><span class="sxs-lookup"><span data-stu-id="d011b-124">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
- <span data-ttu-id="d011b-125">Sie müssen einen Smartcardleser sowie auf dem Computer installierte Treiber haben.</span><span class="sxs-lookup"><span data-stu-id="d011b-125">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
- <span data-ttu-id="d011b-126">Sie müssen das <xref:System.Security.Cryptography.CspParameters>-Objekt mit den entsprechenden Informationen über den Kartenleser initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d011b-126">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="d011b-127">Weitere Informationen finden Sie in der Dokumentation zu Ihrem Kartenleser.</span><span class="sxs-lookup"><span data-stu-id="d011b-127">For more information, see the documentation of your card reader.</span></span>

## <a name="see-also"></a><span data-ttu-id="d011b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d011b-128">See also</span></span>

- [<span data-ttu-id="d011b-129">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="d011b-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="d011b-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="d011b-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="d011b-131">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="d011b-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="d011b-132">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="d011b-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
