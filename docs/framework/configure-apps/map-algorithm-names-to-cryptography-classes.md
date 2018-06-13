---
title: Zuordnen von Algorithmennamen zu kryptografischen Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2dc03c3aa6808ed4ce0c22f4e69fa8c98cb7aebd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758255"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="d8a85-102">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="d8a85-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="d8a85-103">Es gibt vier Möglichkeiten, die ein Entwickler ein Kryptografie-Objekt mithilfe erstellen kann der [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d8a85-103">There are four ways a developer can create a cryptography object using the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span></span>  
  
-   <span data-ttu-id="d8a85-104">Erstellen Sie ein Objekt mithilfe der **neue** Operator.</span><span class="sxs-lookup"><span data-stu-id="d8a85-104">Create an object by using the **new** operator.</span></span>  
  
-   <span data-ttu-id="d8a85-105">Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der **erstellen** Methode in der abstrakten Klasse für diesen Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="d8a85-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
-   <span data-ttu-id="d8a85-106">Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="d8a85-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="d8a85-107">Erstellen Sie ein Objekt, das eine Klasse kryptografischer Algorithmen (z. B. symmetrische Blockchiffre), durch Aufrufen implementiert der **erstellen** Methode in der abstrakten Klasse für diesen Typ des-Algorithmus (z. B. <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="d8a85-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="d8a85-108">Nehmen wir beispielsweise an, dass ein Entwickler möchte den SHA1-Hash einer Reihe von Bytes zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="d8a85-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="d8a85-109">Die <xref:System.Security.Cryptography> -Namespace enthält zwei Implementierungen von den SHA1-Algorithmus, eine rein verwaltete Implementierung und die CryptoAPI umschließt.</span><span class="sxs-lookup"><span data-stu-id="d8a85-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="d8a85-110">Der Entwickler die Möglichkeit, eine bestimmte SHA1-Implementierung instanziieren (z. B. die <xref:System.Security.Cryptography.SHA1Managed>) durch Aufrufen der **neue** Operator.</span><span class="sxs-lookup"><span data-stu-id="d8a85-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="d8a85-111">Wenn es nicht, welche Klasse die common Language Runtime lädt ausschlaggebend, solange die Klasse des SHA1-Hash-Algorithmus implementiert, der Entwickler kann jedoch erstellen ein Objekt durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="d8a85-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d8a85-112">Diese Methode ruft **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1") auf**, muss die eine Implementierung des SHA1-Hashalgorithmus zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d8a85-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="d8a85-113">Der Entwickler kann auch aufrufen **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** da standardmäßig Kryptografiekonfiguration Kurznamen für die Algorithmen, die im Lieferumfang von .NET Framework enthält.</span><span class="sxs-lookup"><span data-stu-id="d8a85-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="d8a85-114">Wenn es nicht ausschlaggebend, welche Hash-Algorithmus verwendet wird, kann der Entwickler rufen die <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> Methode, die ein Objekt zurückgibt, die eine hashing Transformation implementiert.</span><span class="sxs-lookup"><span data-stu-id="d8a85-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="d8a85-115">Zuordnen von Algorithmennamen in Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="d8a85-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="d8a85-116">Standardmäßig gibt die Runtime eine <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> Objekt für alle vier Szenarien.</span><span class="sxs-lookup"><span data-stu-id="d8a85-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="d8a85-117">Ein Computeradministrator kann jedoch den Typ des Objekts ändern, die die Methoden in den letzten beiden Szenarien zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d8a85-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="d8a85-118">Zu diesem Zweck müssen Sie die Klasse ein angezeigte Algorithmusnamen zuordnen, die Sie in der Computerkonfigurationsdatei ("Machine.config") verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d8a85-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="d8a85-119">Im folgende Beispiel wird gezeigt, wie die Common Language Runtime zu konfigurieren, damit **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, und  **System.Security.Cryptography.HashAlgorithm.Create** Zurückgeben einer `MySHA1HashClass` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d8a85-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
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
  
 <span data-ttu-id="d8a85-120">Sie können angeben, den Namen des Attributs in der [< CryptoClass\> Element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (im vorherige Beispiel benennt das Attribut `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="d8a85-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="d8a85-121">Der Wert des Attributs in der  **\<CryptoClass >** Element ist eine Zeichenfolge, die common Language Runtime verwendet die Klasse nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d8a85-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="d8a85-122">Sie können eine beliebige Zeichenfolge, die im angegebenen Anforderungen erfüllt [angeben vollständig gekennzeichneter Typnamen](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="d8a85-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="d8a85-123">Viele Algorithmusnamen können auf die gleiche Klasse zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="d8a85-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="d8a85-124">Die [ \<NameEntry >-Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) einen benutzerfreundlichen Algorithmusname eine Klasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d8a85-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="d8a85-125">Die **Namen** Attribut kann entweder eine Zeichenfolge, die verwendet wird, beim Aufrufen der **System.Security.Cryptography.CryptoConfig.CreateFromName** -Methode oder der Name einer abstrakten kryptografischen Klasse in der <xref:System.Security.Cryptography> Namespace.</span><span class="sxs-lookup"><span data-stu-id="d8a85-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="d8a85-126">Der Wert von der **Klasse** -Attribut ist der Name des Attributs in der  **\<CryptoClass >** Element.</span><span class="sxs-lookup"><span data-stu-id="d8a85-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8a85-127">Sie erhalten einen SHA1-Algorithmus durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> oder **Security.CryptoConfig.CreateFromName("SHA1")** Methode.</span><span class="sxs-lookup"><span data-stu-id="d8a85-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="d8a85-128">Jede Methode ist, gewährleistet lediglich, dass ein Objekt zurückgegeben wird, die den SHA1-Algorithmus implementiert.</span><span class="sxs-lookup"><span data-stu-id="d8a85-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="d8a85-129">Sie müssen nicht jeden Anzeigenamen eines Algorithmus auf die gleiche Klasse in der Konfigurationsdatei zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d8a85-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="d8a85-130">Eine Liste der Standardnamen und die Klassen, denen sie sind zugeordnet, finden Sie unter <xref:System.Security.Cryptography.CryptoConfig>.</span><span class="sxs-lookup"><span data-stu-id="d8a85-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a85-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8a85-131">See Also</span></span>  
 [<span data-ttu-id="d8a85-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="d8a85-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="d8a85-133">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="d8a85-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
