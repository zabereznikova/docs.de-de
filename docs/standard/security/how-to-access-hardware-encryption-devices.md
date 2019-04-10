---
title: 'Vorgehensweise: Zugreifen auf Hardwaregeräte zur Verschlüsselung'
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33af618ac3971df76683fd64346e1aa1e5977177
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334613"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="3d121-102">Vorgehensweise: Zugreifen auf Hardwaregeräte zur Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="3d121-102">How to: Access Hardware Encryption Devices</span></span>
<span data-ttu-id="3d121-103">Mit der <xref:System.Security.Cryptography.CspParameters>-Klasse können Sie auf Verschlüsselungsgeräte zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3d121-103">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="3d121-104">Beispielsweise können Sie diese Klasse dazu verwenden, Ihre Anwendung auf eine Smartcard, einen hardwaremäßigen Zufallszahlengenerator oder eine Hardwareimplementierung eines bestimmten kryptografischen Algorithmus abzustimmen.</span><span class="sxs-lookup"><span data-stu-id="3d121-104">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  
  
 <span data-ttu-id="3d121-105">Die <xref:System.Security.Cryptography.CspParameters>-Klasse erstellt einen Kryptografiedienstanbieter (Cryptographic Service Provider, CSP), der auf ein ordnungsgemäß installiertes Verschlüsselungsgerät zugreift.</span><span class="sxs-lookup"><span data-stu-id="3d121-105">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="3d121-106">Sie können die Verfügbarkeit eines CSP überprüfen, indem die folgenden Registrierungsschlüssel mit dem Registrierungs-Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="3d121-106">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="3d121-107">So signieren Sie Daten mit einer Schlüsselkarte</span><span class="sxs-lookup"><span data-stu-id="3d121-107">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="3d121-108">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.CspParameters>-Klasse, wobei Sie den ganzzahligen Anbietertyp sowie den Anbieternamen an den Konstruktor übergeben</span><span class="sxs-lookup"><span data-stu-id="3d121-108">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="3d121-109">Übergeben Sie die entsprechenden Flags an die <xref:System.Security.Cryptography.CspParameters.Flags%2A>-Eigenschaft des neu erstellten <xref:System.Security.Cryptography.CspParameters>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="3d121-109">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="3d121-110">Übergeben Sie z. B. das <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>-Flag.</span><span class="sxs-lookup"><span data-stu-id="3d121-110">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="3d121-111">Erstellen Sie eine neue Instanz einer <xref:System.Security.Cryptography.AsymmetricAlgorithm>-Klasse (beispielsweise die <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse), wobei Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="3d121-111">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="3d121-112">Signieren Sie Ihre Daten mit einer der `Sign`-Methoden, und überprüfen Sie Ihre Daten mit einer der `Verify`-Methoden.</span><span class="sxs-lookup"><span data-stu-id="3d121-112">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="3d121-113">So generieren Sie eine Zufallszahl mit einem hardwaremäßigen Zufallszahlengenerator </span><span class="sxs-lookup"><span data-stu-id="3d121-113">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="3d121-114">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.CspParameters>-Klasse, wobei Sie den ganzzahligen Anbietertyp sowie den Anbieternamen an den Konstruktor übergeben</span><span class="sxs-lookup"><span data-stu-id="3d121-114">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="3d121-115">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.RNGCryptoServiceProvider>-Klasse, wobei Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="3d121-115">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="3d121-116">Erstellen Sie mit der <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A>-Methode oder der <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>-Methode einen zufälligen Wert.</span><span class="sxs-lookup"><span data-stu-id="3d121-116">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d121-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d121-117">Example</span></span>  
 <span data-ttu-id="3d121-118">Im folgenden Codebeispiel wird veranschaulicht, wie Daten mit einer Smartcard signiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d121-118">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="3d121-119">Im Codebeispiel wird ein <xref:System.Security.Cryptography.CspParameters>-Objekt erstellt, das eine Smartcard verfügbar macht, und anschließend wird mit dem CSP ein <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekt initialisiert.</span><span class="sxs-lookup"><span data-stu-id="3d121-119">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="3d121-120">Danach werden im Codebeispiel einige Daten signiert und überprüft.</span><span class="sxs-lookup"><span data-stu-id="3d121-120">The code example then signs and verifies some data.</span></span>  
  
 [!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
 [!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
 [!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d121-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3d121-121">Compiling the Code</span></span>  
  
-   <span data-ttu-id="3d121-122">Fügen Sie die Namespaces <xref:System> und <xref:System.Security.Cryptography> ein.</span><span class="sxs-lookup"><span data-stu-id="3d121-122">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
-   <span data-ttu-id="3d121-123">Sie müssen einen Smartcardleser sowie auf dem Computer installierte Treiber haben.</span><span class="sxs-lookup"><span data-stu-id="3d121-123">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
-   <span data-ttu-id="3d121-124">Sie müssen das <xref:System.Security.Cryptography.CspParameters>-Objekt mit den entsprechenden Informationen über den Kartenleser initialisieren.</span><span class="sxs-lookup"><span data-stu-id="3d121-124">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="3d121-125">Weitere Informationen finden Sie in der Dokumentation zu Ihrem Kartenleser.</span><span class="sxs-lookup"><span data-stu-id="3d121-125">For more information, see the documentation of your card reader.</span></span>
