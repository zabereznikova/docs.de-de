---
title: Zuordnen von Algorithmennamen zu kryptografischen Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 513000169504473aa6dd46feaca214f58502ffd0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912870"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="9d63e-102">Zuordnen von Algorithmennamen zu kryptografischen Klassen</span><span class="sxs-lookup"><span data-stu-id="9d63e-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="9d63e-103">Es gibt vier Möglichkeiten, wie ein Entwickler ein Kryptografieobjekt mithilfe des Windows SDK erstellen kann:</span><span class="sxs-lookup"><span data-stu-id="9d63e-103">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="9d63e-104">Erstellen Sie ein-Objekt, indem Sie den **New** -Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-104">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="9d63e-105">Erstellen Sie ein Objekt, das einen bestimmten Kryptografiealgorithmus durch Aufrufen der **Create** -Methode für die abstrakte Klasse für diesen Algorithmus implementiert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="9d63e-106">Erstellen Sie ein Objekt, das einen bestimmten Kryptografiealgorithmus implementiert, indem Sie die- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="9d63e-107">Erstellen Sie ein Objekt, das eine Klasse kryptografischer Algorithmen implementiert (z. b. eine symmetrische Blockchiffre), indem Sie die **Create** -Methode für die abstrakte Klasse für diesen Algorithmustyp aufrufen (z <xref:System.Security.Cryptography.SymmetricAlgorithm> . b.).</span><span class="sxs-lookup"><span data-stu-id="9d63e-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="9d63e-108">Nehmen wir beispielsweise an, ein Entwickler möchte den SHA1-Hash eines Satzes von Bytes berechnen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="9d63e-109">Der- <xref:System.Security.Cryptography> Namespace enthält zwei Implementierungen des SHA1-Algorithmus, eine rein verwaltete Implementierung und eine, die CryptoAPI umschließt.</span><span class="sxs-lookup"><span data-stu-id="9d63e-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="9d63e-110">Der Entwickler kann eine bestimmte SHA1-Implementierung (z. b. <xref:System.Security.Cryptography.SHA1Managed> ) durch Aufrufen des **New** -Operators instanziieren.</span><span class="sxs-lookup"><span data-stu-id="9d63e-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="9d63e-111">Wenn es jedoch keine Rolle spielt, welche Klasse das Common Language Runtime lädt, solange die Klasse den SHA1-Hash Algorithmus implementiert, kann der Entwickler ein Objekt durch Aufrufen der- <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9d63e-112">Diese Methode ruft **System. Security. Cryptography. CryptoConfig. kreatefromname ("System. Security. Cryptography. SHA1")** auf, der eine Implementierung des SHA1-Hash Algorithmus zurückgeben muss.</span><span class="sxs-lookup"><span data-stu-id="9d63e-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="9d63e-113">Der Entwickler kann auch **System. Security. Kryptografie. CryptoConfig. kreatefromname ("SHA1")** aufrufen, da die Kryptografiekonfiguration standardmäßig Kurznamen für die Algorithmen enthält, die im .NET Framework ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="9d63e-114">Wenn es keine Rolle spielt, welcher Hash Algorithmus verwendet wird, kann der Entwickler die-Methode aufzurufen <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> , die ein Objekt zurückgibt, das eine Hash Transformation implementiert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="9d63e-115">Mapping von Algorithmusnamen in Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="9d63e-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="9d63e-116">Standardmäßig gibt die Laufzeit ein- <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> Objekt für alle vier Szenarien zurück.</span><span class="sxs-lookup"><span data-stu-id="9d63e-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="9d63e-117">Ein Computer Administrator kann jedoch den Objekttyp ändern, den die Methoden in den letzten beiden Szenarien zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9d63e-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="9d63e-118">Zu diesem Zweck müssen Sie der Klasse, die Sie in der Computer Konfigurationsdatei (Machine. config) verwenden möchten, einen anzeigen Amen für den Algorithmus zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="9d63e-119">Im folgenden Beispiel wird gezeigt, wie die Laufzeit so konfiguriert wird, dass **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. kreatefromname ("SHA1")** und **System. Security. Cryptography. HashAlgorithm. Create** ein-Objekt zurückgeben `MySHA1HashClass` .</span><span class="sxs-lookup"><span data-stu-id="9d63e-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
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
  
 <span data-ttu-id="9d63e-120">Sie können den Namen des Attributs im [<CryptoClass- \> Element](./file-schema/cryptography/cryptoclass-element.md) angeben (im vorherigen Beispiel wird das-Attribut benannt `MySHA1Hash` ).</span><span class="sxs-lookup"><span data-stu-id="9d63e-120">You can specify the name of the attribute in the [<cryptoClass\> element](./file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="9d63e-121">Der Wert des-Attributs im- **\<cryptoClass>** Element ist eine Zeichenfolge, die der Common Language Runtime verwendet, um die-Klasse zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="9d63e-122">Sie können jede beliebige Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="9d63e-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="9d63e-123">Viele Algorithmusnamen können derselben Klasse zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="9d63e-124">Das- [ \<nameEntry> Element](./file-schema/cryptography/nameentry-element.md) ordnet eine Klasse einem benutzerfreundlichen Algorithmusnamen zu.</span><span class="sxs-lookup"><span data-stu-id="9d63e-124">The [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="9d63e-125">Das **Name** -Attribut kann entweder eine Zeichenfolge sein, die beim Aufrufen der **System. Security. Kryptografie. CryptoConfig. CreateFromName** -Methode oder der Name einer abstrakten Kryptografieklasse im- <xref:System.Security.Cryptography> Namespace verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d63e-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="9d63e-126">Der Wert des **Class** -Attributs ist der Name des Attributs im- **\<cryptoClass>** Element.</span><span class="sxs-lookup"><span data-stu-id="9d63e-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d63e-127">Sie können einen SHA1-Algorithmus abrufen, indem Sie die- <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode oder die **Security. CryptoConfig. CreateFromName ("SHA1")** -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="9d63e-128">Jede Methode garantiert nur, dass Sie ein Objekt zurückgibt, das den SHA1-Algorithmus implementiert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="9d63e-129">Sie müssen nicht jeden anzeigen Amen eines Algorithmus derselben Klasse in der Konfigurationsdatei zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="9d63e-130">Eine Liste der Standardnamen und der Klassen, denen Sie zugeordnet sind, finden Sie unter <xref:System.Security.Cryptography.CryptoConfig> .</span><span class="sxs-lookup"><span data-stu-id="9d63e-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d63e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d63e-131">See also</span></span>

- [<span data-ttu-id="9d63e-132">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="9d63e-132">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="9d63e-133">Konfigurieren kryptografischer Klassen</span><span class="sxs-lookup"><span data-stu-id="9d63e-133">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
