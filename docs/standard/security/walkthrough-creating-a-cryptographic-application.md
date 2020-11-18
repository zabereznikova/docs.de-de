---
title: 'Exemplarische Vorgehensweise: Erstellen einer kryptografischen Anwendung'
description: 'Exemplarische Vorgehensweise: Erstellen einer kryptografischen Anwendung Erfahren Sie, wie Sie Inhalte in einer Windows Forms Anwendung verschlüsseln und entschlüsseln.'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET], example
- cryptography [NET], cryptographic application example
- cryptography [NET], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 70218d60abb336cdb35fc2e89e62a50b6bd79c67
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830557"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="1c494-104">Exemplarische Vorgehensweise: Erstellen einer kryptografischen Anwendung</span><span class="sxs-lookup"><span data-stu-id="1c494-104">Walkthrough: Creating a Cryptographic Application</span></span>

> [!NOTE]
> <span data-ttu-id="1c494-105">Dieser Artikel bezieht sich auf Windows.</span><span class="sxs-lookup"><span data-stu-id="1c494-105">This article applies to Windows.</span></span>
>
> <span data-ttu-id="1c494-106">Weitere Informationen zu ASP.net Core finden Sie unter [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="1c494-106">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="1c494-107">Diese exemplarische Vorgehensweise veranschaulicht, wie Inhalt verschlüsselt und entschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="1c494-107">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="1c494-108">Die Codebeispiele sind für eine Windows Forms-Anwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1c494-108">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="1c494-109">Diese Anwendung zeigt keine realen Szenarien wie die Verwendung von Smartcards.</span><span class="sxs-lookup"><span data-stu-id="1c494-109">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="1c494-110">Stattdessen veranschaulicht sie die Grundlagen der Ver- und Entschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="1c494-110">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
<span data-ttu-id="1c494-111">In dieser exemplarische Vorgehensweise werden die folgenden Richtlinien für Verschlüsselung verwendet:</span><span class="sxs-lookup"><span data-stu-id="1c494-111">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="1c494-112">Verwenden Sie die <xref:System.Security.Cryptography.Aes>-Klasse (ein symmetrischer Algorithmus), um Daten zu ver- und entschlüsseln, indem Sie den automatisch generierten Schlüssel (<xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A>) und Initialisierungsvektor (<xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c494-112">Use the <xref:System.Security.Cryptography.Aes> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="1c494-113">Verwenden <xref:System.Security.Cryptography.RSA> Sie den asymmetrischen Algorithmus, um den Schlüssel für die von verschlüsselten Daten zu verschlüsseln und zu entschlüsseln <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="1c494-113">Use the <xref:System.Security.Cryptography.RSA> asymmetric algorithm to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.Aes>.</span></span> <span data-ttu-id="1c494-114">Asymmetrische Algorithmen sind am besten für kleinere Datenmengen geeignet, zum Beispiel für einen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="1c494-114">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1c494-115">Wenn Sie Daten auf Ihrem Computer schützen möchten, anstatt verschlüsselte Inhalte mit anderen Personen auszutauschen, sollten Sie die Verwendung der-Klasse in Erwägung gezogen <xref:System.Security.Cryptography.ProtectedData> .</span><span class="sxs-lookup"><span data-stu-id="1c494-115">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> class.</span></span>  
  
 <span data-ttu-id="1c494-116">In der folgenden Tabelle sind die kryptografischen Aufgaben in diesem Thema zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="1c494-116">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="1c494-117">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="1c494-117">Task</span></span>|<span data-ttu-id="1c494-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1c494-118">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1c494-119">Erstellen einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="1c494-119">Creating a Windows Forms application</span></span>|<span data-ttu-id="1c494-120">Listet die Steuerelemente auf, die zum Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1c494-120">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="1c494-121">Deklarieren von globalen Objekten</span><span class="sxs-lookup"><span data-stu-id="1c494-121">Declaring global objects</span></span>|<span data-ttu-id="1c494-122">Deklariert Zeichenfolgenpfadvariablen, die <xref:System.Security.Cryptography.CspParameters> und den <xref:System.Security.Cryptography.RSACryptoServiceProvider>, um den globalen Kontext der <xref:System.Windows.Forms.Form>-Klasse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c494-122">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="1c494-123">Erstellen eines asymmetrischen Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-123">Creating an asymmetric key</span></span>|<span data-ttu-id="1c494-124">Erstellt ein asymmetrisches öffentliches und privates Schlüsselwertpaar und weist ihm einen Schlüsselcontainernamen zu.</span><span class="sxs-lookup"><span data-stu-id="1c494-124">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="1c494-125">Verschlüsseln einer Datei</span><span class="sxs-lookup"><span data-stu-id="1c494-125">Encrypting a file</span></span>|<span data-ttu-id="1c494-126">Zeigt ein Dialogfeld an, in dem eine Datei für die Verschlüsselung ausgewählt wird, und verschlüsselt die Datei.</span><span class="sxs-lookup"><span data-stu-id="1c494-126">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="1c494-127">Entschlüsseln einer Datei</span><span class="sxs-lookup"><span data-stu-id="1c494-127">Decrypting a file</span></span>|<span data-ttu-id="1c494-128">Zeigt ein Dialogfeld an, in dem eine verschlüsselte Datei für die Entschlüsselung ausgewählt wird, und entschlüsselt die Datei.</span><span class="sxs-lookup"><span data-stu-id="1c494-128">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="1c494-129">Abrufen eines privaten Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-129">Getting a private key</span></span>|<span data-ttu-id="1c494-130">Ruft das volle Schlüsselpaar über den Schlüsselcontainernamen ab.</span><span class="sxs-lookup"><span data-stu-id="1c494-130">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="1c494-131">Exportieren eines öffentlichen Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-131">Exporting a public key</span></span>|<span data-ttu-id="1c494-132">Speichert den Schlüssel in einer XML-Datei mit ausschließlich öffentlichen Parametern.</span><span class="sxs-lookup"><span data-stu-id="1c494-132">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="1c494-133">Importieren eines öffentlichen Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-133">Importing a public key</span></span>|<span data-ttu-id="1c494-134">Lädt den Schlüssel aus einer XML-Datei in den Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="1c494-134">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="1c494-135">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="1c494-135">Testing the application</span></span>|<span data-ttu-id="1c494-136">Listet Verfahren zum Testen dieser Anwendung auf.</span><span class="sxs-lookup"><span data-stu-id="1c494-136">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="1c494-137">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1c494-137">Prerequisites</span></span>  

<span data-ttu-id="1c494-138">Zum Abschließen dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1c494-138">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="1c494-139">Verweise auf die Namespaces <xref:System.IO> und <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="1c494-139">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="1c494-140">Erstellen einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="1c494-140">Creating a Windows Forms Application</span></span>  

<span data-ttu-id="1c494-141">Die meisten Codebeispiele in dieser exemplarischen Vorgehensweise sind als Ereignishandler für Button-Steuerelemente konzipiert.</span><span class="sxs-lookup"><span data-stu-id="1c494-141">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="1c494-142">In der folgenden Tabelle sind die Steuerelemente aufgelistet, die für die Beispielanwendung und die erforderlichen Namen benötigt werden, um mit den Codebeispielen übereinzustimmen.</span><span class="sxs-lookup"><span data-stu-id="1c494-142">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="1c494-143">Control</span><span class="sxs-lookup"><span data-stu-id="1c494-143">Control</span></span>|<span data-ttu-id="1c494-144">Name</span><span class="sxs-lookup"><span data-stu-id="1c494-144">Name</span></span>|<span data-ttu-id="1c494-145">Texteigenschaft (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="1c494-145">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="1c494-146">Datei verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="1c494-146">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="1c494-147">Datei entschlüsseln</span><span class="sxs-lookup"><span data-stu-id="1c494-147">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="1c494-148">Schlüssel erstellen</span><span class="sxs-lookup"><span data-stu-id="1c494-148">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="1c494-149">Öffentlichen Schlüssel exportieren</span><span class="sxs-lookup"><span data-stu-id="1c494-149">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="1c494-150">Öffentlichen Schlüssel importieren</span><span class="sxs-lookup"><span data-stu-id="1c494-150">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="1c494-151">Privaten Schlüssel abrufen</span><span class="sxs-lookup"><span data-stu-id="1c494-151">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="1c494-152">Schlüssel nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="1c494-152">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="1c494-153">Doppelklicken Sie auf die Schaltflächen im Visual Studio-Designer, um deren Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c494-153">Double-click the buttons in the Visual Studio designer to create their event handlers.</span></span>
  
## <a name="declaring-global-objects"></a><span data-ttu-id="1c494-154">Deklarieren von globalen Objekten</span><span class="sxs-lookup"><span data-stu-id="1c494-154">Declaring Global Objects</span></span>  

<span data-ttu-id="1c494-155">Fügen Sie dem Konstruktor des Form-Objekts folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c494-155">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="1c494-156">Bearbeiten Sie die Zeichenfolgenvariablen für Ihre Umgebung und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="1c494-156">Edit the string variables for your environment and preferences.</span></span>  
  
[!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
[!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="1c494-157">Erstellen eines asymmetrischen Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-157">Creating an Asymmetric Key</span></span>  

<span data-ttu-id="1c494-158">Mit dieser Aufgabe wird ein asymmetrischer Schlüssel erstellt, der den <xref:System.Security.Cryptography.Aes>-Schlüssel ver- und entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="1c494-158">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.Aes> key.</span></span> <span data-ttu-id="1c494-159">Dieser Schlüssel wurde verwendet, um den Inhalt zu verschlüsseln, und zeigt den Schlüsselcontainernamen auf dem Label-Steuerelement an.</span><span class="sxs-lookup"><span data-stu-id="1c494-159">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="1c494-160">Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Create Keys`-Schaltfläche hinzu (`buttonCreateAsmKeys_Click`).</span><span class="sxs-lookup"><span data-stu-id="1c494-160">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="1c494-161">Verschlüsseln einer Datei</span><span class="sxs-lookup"><span data-stu-id="1c494-161">Encrypting a File</span></span>  

<span data-ttu-id="1c494-162">Diese Aufgabe umfasst zwei Methoden: die Ereignishandlermethode für die `Encrypt File` Schaltfläche ( `buttonEncryptFile_Click` ) und die- `EncryptFile` Methode.</span><span class="sxs-lookup"><span data-stu-id="1c494-162">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="1c494-163">Die erste Methode zeigt ein Dialogfeld zum Auswählen einer Datei an und übergibt den Dateinamen an die zweite Methode, die die Verschlüsselung ausführt.</span><span class="sxs-lookup"><span data-stu-id="1c494-163">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
<span data-ttu-id="1c494-164">Der verschlüsselte Inhalt, der Schlüssel und der IV werden zusammen in einem <xref:System.IO.FileStream>-Objekt gespeichert, das als Verschlüsselungspaket bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="1c494-164">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
<span data-ttu-id="1c494-165">Die `EncryptFile`-Methode führt folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1c494-165">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="1c494-166">Sie erstellt einen symmetrischen <xref:System.Security.Cryptography.Aes>-Algorithmus, um den Inhalt zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1c494-166">Creates a <xref:System.Security.Cryptography.Aes> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="1c494-167">Sie erstellt ein <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekt, um den <xref:System.Security.Cryptography.Aes>-Schlüssel zu verschlüsseln. </span><span class="sxs-lookup"><span data-stu-id="1c494-167">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
3. <span data-ttu-id="1c494-168">Sie verwendet ein <xref:System.Security.Cryptography.CryptoStream>-Objekt, um den <xref:System.IO.FileStream> der Quelldatei in Byteblöcken in ein Ziel-<xref:System.IO.FileStream>-Objekt für die verschlüsselte Datei zu lesen und zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1c494-168">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="1c494-169">Sie ermittelt die Länge des verschlüsselten Schlüssels und IVs und erstellt Bytearrays mit deren Längenwerten.</span><span class="sxs-lookup"><span data-stu-id="1c494-169">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="1c494-170">Sie schreibt den Schlüssel, den IV und deren Längenwerte in das verschlüsselte Paket.</span><span class="sxs-lookup"><span data-stu-id="1c494-170">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="1c494-171">Das Verschlüsselungspaket hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="1c494-171">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="1c494-172">Schlüssellänge, Bytes 0 - 3</span><span class="sxs-lookup"><span data-stu-id="1c494-172">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="1c494-173">IV-Länge, Bytes 4 - 7</span><span class="sxs-lookup"><span data-stu-id="1c494-173">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="1c494-174">Verschlüsselte Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1c494-174">Encrypted key</span></span>  
  
- <span data-ttu-id="1c494-175">IV</span><span class="sxs-lookup"><span data-stu-id="1c494-175">IV</span></span>  
  
- <span data-ttu-id="1c494-176">Verschlüsselungsverfahrenstext</span><span class="sxs-lookup"><span data-stu-id="1c494-176">Cipher text</span></span>  
  
 <span data-ttu-id="1c494-177">Durch die Längenangaben für den Schlüssel und den IV lassen sich Startpunkte und Längen aller Teile des Verschlüsselungspakets bestimmen. Diese können dann zum Entschlüsseln der Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c494-177">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="1c494-178">Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Encrypt File`-Schaltfläche hinzu (`buttonEncryptFile_Click`).</span><span class="sxs-lookup"><span data-stu-id="1c494-178">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="1c494-179">Fügen Sie dem Form-Objekt die folgende `EncryptFile`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c494-179">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="1c494-180">Entschlüsseln einer Datei</span><span class="sxs-lookup"><span data-stu-id="1c494-180">Decrypting a File</span></span>  

<span data-ttu-id="1c494-181">Diese Aufgabe bedingt zwei Methoden: die Ereignishandlermethode für die `Decrypt File`-Schaltfläche (`buttonDecryptFile_Click`) und die `DecryptFile`-Methode.</span><span class="sxs-lookup"><span data-stu-id="1c494-181">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="1c494-182">Die erste Methode zeigt ein Dialogfeld zum Auswählen einer Datei an und übergibt den Dateinamen an die zweite Methode, die die Entschlüsselung ausführt.</span><span class="sxs-lookup"><span data-stu-id="1c494-182">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
<span data-ttu-id="1c494-183">Die `Decrypt`-Methode führt folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1c494-183">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="1c494-184">Erstellt einen <xref:System.Security.Cryptography.Aes> symmetrischen Algorithmus, um den Inhalt zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1c494-184">Creates an <xref:System.Security.Cryptography.Aes> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="1c494-185">Sie liest die ersten acht Bytes des <xref:System.IO.FileStream>-Objekts des verschlüsselten Pakets in Bytearrays ein, um die Länge des verschlüsselten Schlüssels und IVs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c494-185">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="1c494-186">Sie extrahiert den Schlüssel und den IV aus dem Verschlüsselungspaket in Bytearrays hinein.</span><span class="sxs-lookup"><span data-stu-id="1c494-186">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="1c494-187">Sie erstellt ein <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekt, um den <xref:System.Security.Cryptography.Aes>-Schlüssel zu entschlüsseln. </span><span class="sxs-lookup"><span data-stu-id="1c494-187">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
5. <span data-ttu-id="1c494-188">Sie verwendet ein <xref:System.Security.Cryptography.CryptoStream>-Objekt, um den Verschlüsselungsverfahrenstext-Abschnitt des <xref:System.IO.FileStream>-Verschlüsselungspakets als Byteblöcke in das <xref:System.IO.FileStream>-Objekt für die verschlüsselte Datei einzulesen und zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1c494-188">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="1c494-189">Nach Beendigung dieses Vorgangs ist die Entschlüsselung abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1c494-189">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="1c494-190">Fügen Sie folgenden Code als `Click`-Ereignishandler für die Schaltfläche `Decrypt File` hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c494-190">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="1c494-191">Fügen Sie dem Form-Objekt die folgende `DecryptFile`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c494-191">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="1c494-192">Exportieren eines öffentlichen Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-192">Exporting a Public Key</span></span>

<span data-ttu-id="1c494-193">In dieser Aufgabe wird der über die Schaltfläche `Create Keys` erstellte Schlüssel in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c494-193">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="1c494-194">Es werden nur die öffentlichen Parameter exportiert.</span><span class="sxs-lookup"><span data-stu-id="1c494-194">It exports only the public parameters.</span></span>  
  
<span data-ttu-id="1c494-195">In dieser Aufgabe wird das Szenario simuliert, in dem Alice ihren öffentlichen Schlüssel Bob gibt, sodass er Dateien an sie verschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="1c494-195">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="1c494-196">Er und andere, die im Besitz dieses öffentlichen Schlüssels sind, können die Dateien nicht entschlüsseln, da sie nicht das vollständige Schlüsselpaar mit privaten Parametern haben.</span><span class="sxs-lookup"><span data-stu-id="1c494-196">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="1c494-197">Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Export Public Key`-Schaltfläche hinzu (`buttonExportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="1c494-197">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
[!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="1c494-198">Importieren eines öffentlichen Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-198">Importing a Public Key</span></span>

<span data-ttu-id="1c494-199">In dieser Aufgabe wird der Schlüssel mit ausschließlich öffentlichen Parametern, wie er über die Schaltfläche `Export Public Key` erstellt wurde, geladen und als Schlüsselcontainername festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1c494-199">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
<span data-ttu-id="1c494-200">In dieser Aufgabe wird das Szenario simuliert, in dem Bob den Schlüssel von Alice mit ausschließlich öffentlichen Parametern lädt, sodass er Dateien an sie verschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="1c494-200">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
<span data-ttu-id="1c494-201">Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Import Public Key`-Schaltfläche hinzu (`buttonImportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="1c494-201">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
[!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="1c494-202">Abrufen eines privaten Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1c494-202">Getting a Private Key</span></span>  

<span data-ttu-id="1c494-203">In dieser Aufgabe wird der Schlüsselcontainername auf den Namen des Schlüssels festgelegt, der über die Schaltfläche `Create Keys` erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1c494-203">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="1c494-204">Der Schlüsselcontainer enthält das komplette Schlüsselpaar mit privaten Parametern.</span><span class="sxs-lookup"><span data-stu-id="1c494-204">The key container will contain the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="1c494-205">In dieser Aufgabe wird das Szenario simuliert, in dem Alice ihren privaten Schlüssel dazu verwendet, Dateien zu entschlüsseln, die von Bob verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="1c494-205">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
<span data-ttu-id="1c494-206">Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Get Private Key`-Schaltfläche hinzu (`buttonGetPrivateKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="1c494-206">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
[!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="1c494-207">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="1c494-207">Testing the Application</span></span>

<span data-ttu-id="1c494-208">Nachdem Sie die Anwendung erstellt haben, führen Sie die folgenden Testszenarien aus.</span><span class="sxs-lookup"><span data-stu-id="1c494-208">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="1c494-209">So erstellen Sie Schlüssel, so ver- und entschlüsseln Sie</span><span class="sxs-lookup"><span data-stu-id="1c494-209">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="1c494-210">Klicken Sie auf die Schaltfläche `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="1c494-210">Click the `Create Keys` button.</span></span> <span data-ttu-id="1c494-211">Die Bezeichnung zeigt den Schlüsselnamen an und zeigt, dass es sich um ein vollständiges Schlüsselpaar handelt.</span><span class="sxs-lookup"><span data-stu-id="1c494-211">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="1c494-212">Klicken Sie auf die Schaltfläche `Export Public Key`.</span><span class="sxs-lookup"><span data-stu-id="1c494-212">Click the `Export Public Key` button.</span></span> <span data-ttu-id="1c494-213">Durch das Exportieren der öffentlichen Schlüsselparameter wird der aktuelle Schlüssel nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="1c494-213">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="1c494-214">Klicken Sie auf die Schaltfläche `Encrypt File`, und wählen Sie eine Datei aus.</span><span class="sxs-lookup"><span data-stu-id="1c494-214">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="1c494-215">Klicken Sie auf die Schaltfläche `Decrypt File`, und wählen Sie die soeben verschlüsselte Datei aus.</span><span class="sxs-lookup"><span data-stu-id="1c494-215">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="1c494-216">Sehen Sie sich die nun entschlüsselte Datei an.</span><span class="sxs-lookup"><span data-stu-id="1c494-216">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="1c494-217">Schließen Sie die Anwendung, und starten Sie sie neu, um das Abrufen von beibehaltenen Schlüsselcontainern im nächsten Szenario zu testen.</span><span class="sxs-lookup"><span data-stu-id="1c494-217">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="1c494-218">So verschlüsseln Sie mit dem öffentlichen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1c494-218">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="1c494-219">Klicken Sie auf die Schaltfläche `Import Public Key`.</span><span class="sxs-lookup"><span data-stu-id="1c494-219">Click the `Import Public Key` button.</span></span> <span data-ttu-id="1c494-220">Die Bezeichnung zeigt den Schlüsselnamen an und zeigt, dass dies nur der öffentliche Schlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="1c494-220">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="1c494-221">Klicken Sie auf die Schaltfläche `Encrypt File`, und wählen Sie eine Datei aus.</span><span class="sxs-lookup"><span data-stu-id="1c494-221">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="1c494-222">Klicken Sie auf die Schaltfläche `Decrypt File`, und wählen Sie die soeben verschlüsselte Datei aus.</span><span class="sxs-lookup"><span data-stu-id="1c494-222">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="1c494-223">Dieser Schritt schlägt fehl, weil Sie für das Entschlüsseln den privaten Schlüssel haben müssen.</span><span class="sxs-lookup"><span data-stu-id="1c494-223">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="1c494-224">Dieses Szenario veranschaulicht, wie mit ausschließlich dem öffentlichen Schlüssel eine Datei für eine andere Person verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="1c494-224">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="1c494-225">Normalerweise würde diese Person Ihnen nur den öffentlichen Schlüssel geben und den privaten Schlüssel für Entschlüsselung zurückbehalten.</span><span class="sxs-lookup"><span data-stu-id="1c494-225">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="1c494-226">So entschlüsseln Sie mit dem privaten Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1c494-226">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="1c494-227">Klicken Sie auf die Schaltfläche `Get Private Key`.</span><span class="sxs-lookup"><span data-stu-id="1c494-227">Click the `Get Private Key` button.</span></span> <span data-ttu-id="1c494-228">Die Bezeichnung zeigt den Schlüsselnamen an und zeigt, ob es sich um das vollständige Schlüsselpaar handelt.</span><span class="sxs-lookup"><span data-stu-id="1c494-228">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="1c494-229">Klicken Sie auf die Schaltfläche `Decrypt File`, und wählen Sie die soeben verschlüsselte Datei aus.</span><span class="sxs-lookup"><span data-stu-id="1c494-229">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="1c494-230">Dies ist erfolgreich, weil Sie das vollständige Schlüsselpaar zum Entschlüsseln haben.</span><span class="sxs-lookup"><span data-stu-id="1c494-230">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c494-231">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c494-231">See also</span></span>

- <span data-ttu-id="1c494-232">[Kryptografiemodell](cryptography-model.md) : Beschreibt, wie Kryptografie in der Basisklassen Bibliothek implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="1c494-232">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="1c494-233">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="1c494-233">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="1c494-234">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="1c494-234">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="1c494-235">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="1c494-235">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
