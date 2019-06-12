---
title: Zuordnen von Algorithmennamen zu kryptografischen Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: c76f80273d37f838ca52efd3b8f8c028b76a4d30
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832687"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="94aec-102">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="94aec-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="94aec-103">Es gibt vier Möglichkeiten, die ein Entwickler ein Kryptografieobjekts, verwenden das Windows Software Development Kit (SDK) erstellen kann:</span><span class="sxs-lookup"><span data-stu-id="94aec-103">There are four ways a developer can create a cryptography object using the Windows Software Development Kit (SDK):</span></span>  
  
- <span data-ttu-id="94aec-104">Erstellen Sie ein Objekt mithilfe der **neue** Operator.</span><span class="sxs-lookup"><span data-stu-id="94aec-104">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="94aec-105">Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der **erstellen** Methode für die abstrakte Klasse für diesen Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="94aec-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="94aec-106">Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="94aec-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="94aec-107">Erstellen Sie ein Objekt, das implementiert, eine Klasse von kryptografischen Algorithmen (z. B. eine Verschlüsselung symmetrischer Blöcke) durch Aufrufen der **erstellen** Methode für die abstrakte Klasse für diesen Typ des-Algorithmus (z. B. <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="94aec-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="94aec-108">Nehmen wir beispielsweise an, dass ein Entwickler möchte, um den SHA1-Hash einer Reihe von Bytes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="94aec-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="94aec-109">Die <xref:System.Security.Cryptography> -Namespace enthält zwei Implementierungen von SHA1-Algorithmus, eine rein verwaltete Implementierungen und diejenige, die CryptoAPI umschließt.</span><span class="sxs-lookup"><span data-stu-id="94aec-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="94aec-110">Entwickler kann auch eine bestimmte Implementierung des SHA1 instanziieren (z. B. die <xref:System.Security.Cryptography.SHA1Managed>) durch Aufrufen der **neue** Operator.</span><span class="sxs-lookup"><span data-stu-id="94aec-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="94aec-111">Jedoch wenn es keine, welche Klasse die common Language Runtime lädt Rolle, solange die Klasse des SHA1-Hash-Algorithmus implementiert, der Entwickler kann erstellen ein Objekt durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="94aec-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="94aec-112">Diese Methode ruft **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1") auf**, womit muss eine Implementierung des SHA1-Hashalgorithmus zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94aec-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="94aec-113">Entwickler kann auch aufrufen, **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** daran, dass standardmäßig die Kryptografiekonfiguration kurze Namen für die Algorithmen, die im Lieferumfang von .NET Framework enthält.</span><span class="sxs-lookup"><span data-stu-id="94aec-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="94aec-114">Wenn es keine Rolle spielt die Hashalgorithmus verwendet wird, kann der Entwickler Aufrufen der <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> Methode, die ein Objekt zurückgibt, die eine Transformation Hashalgorithmus implementiert.</span><span class="sxs-lookup"><span data-stu-id="94aec-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="94aec-115">Zuordnen von Algorithmennamen in Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="94aec-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="94aec-116">Standardmäßig gibt die Runtime eine <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> -Objekt für alle vier Szenarien.</span><span class="sxs-lookup"><span data-stu-id="94aec-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="94aec-117">Ein Computeradministrator kann jedoch den Typ des Objekts ändern, die die Methoden in den letzten beiden Szenarien zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="94aec-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="94aec-118">Zu diesem Zweck müssen Sie einen Namen für die Anzeigenamen von Algorithmen für die Klasse zuordnen, die Sie in der Computerkonfigurationsdatei (Machine.config) verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="94aec-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="94aec-119">Das folgende Beispiel zeigt, wie die Laufzeit so konfiguriert, damit **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")** , und  **System.Security.Cryptography.HashAlgorithm.Create** Zurückgeben einer `MySHA1HashClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="94aec-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="94aec-120">Sie können angeben, den Namen des Attributs in der [< CryptoClass\> Element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (im vorherige Beispiel benennt das Attribut `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="94aec-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="94aec-121">Der Wert des Attributs in der  **\<CryptoClass >** Element ist eine Zeichenfolge, die die common Language Runtime verwendet wird, um die Klasse zu finden.</span><span class="sxs-lookup"><span data-stu-id="94aec-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="94aec-122">Sie können eine beliebige Zeichenfolge, die die in angegebenen Anforderungen erfüllt [angeben vollständig gekennzeichneter Typnamen](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="94aec-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="94aec-123">Viele können Algorithmen die gleiche Klasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="94aec-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="94aec-124">Die [ \<NameEntry >-Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) einen Anzeigenamen von Algorithmusnamen eine Klasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="94aec-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="94aec-125">Die **Namen** Attribut kann entweder eine Zeichenfolge, die verwendet wird, beim Aufrufen von sein der **System.Security.Cryptography.CryptoConfig.CreateFromName** Methode oder den Namen einer abstrakten kryptografischen Klasse in der <xref:System.Security.Cryptography> Namespace.</span><span class="sxs-lookup"><span data-stu-id="94aec-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="94aec-126">Der Wert des der **Klasse** Attribut ist der Name des Attributs in der  **\<CryptoClass >** Element.</span><span class="sxs-lookup"><span data-stu-id="94aec-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94aec-127">Sie erhalten einen SHA1-Algorithmus durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> oder **Security.CryptoConfig.CreateFromName("SHA1")** Methode.</span><span class="sxs-lookup"><span data-stu-id="94aec-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="94aec-128">Jede Methode garantiert nur an, dass es sich um ein Objekt zurückgibt, die den SHA1-Algorithmus implementiert.</span><span class="sxs-lookup"><span data-stu-id="94aec-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="94aec-129">Sie müssen nicht jede Anzeigenamen eines Algorithmus auf dieselbe Klasse in der Konfigurationsdatei zuordnen.</span><span class="sxs-lookup"><span data-stu-id="94aec-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="94aec-130">Eine Liste der Namen für Standardwerte und die Klassen, die sie sind zugeordnet, finden Sie unter <xref:System.Security.Cryptography.CryptoConfig>.</span><span class="sxs-lookup"><span data-stu-id="94aec-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94aec-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94aec-131">See also</span></span>

- [<span data-ttu-id="94aec-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="94aec-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="94aec-133">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="94aec-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
