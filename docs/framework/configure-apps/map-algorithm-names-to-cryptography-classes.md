---
title: Zuordnen von Algorithmennamen zu kryptografischen Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 49f4b5b4b3634df5e648b5208448d644168e9d19
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566724"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Zuordnen von Algorithmennamen zu kryptografischen Klassen
Es gibt vier Möglichkeiten, wie ein Entwickler ein Kryptografieobjekt mithilfe des Windows SDK erstellen kann:  
  
- Erstellen Sie ein-Objekt, indem Sie den **New** -Operator verwenden.  
  
- Erstellen Sie ein Objekt, das einen bestimmten Kryptografiealgorithmus durch Aufrufen der **Create** -Methode für die abstrakte Klasse für diesen Algorithmus implementiert.  
  
- Erstellen Sie ein Objekt, das einen bestimmten Kryptografiealgorithmus implementiert <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> , indem Sie die-Methode aufrufen.  
  
- Erstellen Sie ein Objekt, das eine Klasse kryptografischer Algorithmen implementiert (z. b. eine symmetrische Blockchiffre), indem Sie die **Create** -Methode für die abstrakte Klasse für diesen Algorithmustyp aufrufen (z <xref:System.Security.Cryptography.SymmetricAlgorithm>. b.).  
  
 Nehmen wir beispielsweise an, ein Entwickler möchte den SHA1-Hash eines Satzes von Bytes berechnen. Der <xref:System.Security.Cryptography> -Namespace enthält zwei Implementierungen des SHA1-Algorithmus, eine rein verwaltete Implementierung und eine, die CryptoAPI umschließt. Der Entwickler kann eine bestimmte SHA1-Implementierung (z <xref:System.Security.Cryptography.SHA1Managed>. b.) durch Aufrufen des **New** -Operators instanziieren. Wenn es jedoch keine Rolle spielt, welche Klasse das Common Language Runtime lädt, solange die Klasse den SHA1-Hash Algorithmus implementiert, kann der Entwickler ein Objekt durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> -Methode erstellen. Diese Methode ruft **System. Security. Cryptography. CryptoConfig. kreatefromname ("System. Security. Cryptography. SHA1")** auf, der eine Implementierung des SHA1-Hash Algorithmus zurückgeben muss.  
  
 Der Entwickler kann auch **System. Security. Kryptografie. CryptoConfig. kreatefromname ("SHA1")** aufrufen, da die Kryptografiekonfiguration standardmäßig Kurznamen für die Algorithmen enthält, die im .NET Framework ausgeliefert werden.  
  
 Wenn es keine Rolle spielt, welcher Hash Algorithmus verwendet wird, kann der Entwickler die <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> -Methode aufzurufen, die ein Objekt zurückgibt, das eine Hash Transformation implementiert.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Mapping von Algorithmusnamen in Konfigurationsdateien  
 Standardmäßig gibt die Laufzeit ein <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> -Objekt für alle vier Szenarien zurück. Ein Computer Administrator kann jedoch den Objekttyp ändern, den die Methoden in den letzten beiden Szenarien zurückgegeben haben. Zu diesem Zweck müssen Sie der Klasse, die Sie in der Computer Konfigurationsdatei (Machine. config) verwenden möchten, einen anzeigen Amen für den Algorithmus zuordnen.  
  
 Im folgenden Beispiel wird gezeigt, wie die Laufzeit so konfiguriert wird, dass **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. kreatefromname ("SHA1")** und **System. Security. Cryptography. HashAlgorithm. Create** gibt ein `MySHA1HashClass` -Objekt zurück.  
  
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
  
 Sie können den Namen des Attributs im [< CryptoClass\> -Element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) angeben (im vorherigen Beispiel wird das- `MySHA1Hash`Attribut benannt). Der Wert des-Attributs im  **\<cryptoClass->** -Element ist eine Zeichenfolge, die der Common Language Runtime verwendet, um die-Klasse zu suchen. Sie können jede beliebige Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.  
  
 Viele Algorithmusnamen können derselben Klasse zugeordnet werden. Das [ \<nameEntry-> Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) ordnet eine Klasse einem anzeigen amen des Algorithmus zu. Das **Name** -Attribut kann entweder eine Zeichenfolge sein, die beim Aufrufen der **System. Security. Kryptografie. CryptoConfig. CreateFromName** -Methode oder der Name einer abstrakten <xref:System.Security.Cryptography> Kryptografieklasse im-Namespace verwendet wird. Der Wert des **Class** -Attributs ist der Name des Attributs im  **\<cryptoClass->** Element.  
  
> [!NOTE]
>  Sie können einen SHA1-Algorithmus abrufen, indem <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Sie die-Methode oder die **Security. CryptoConfig. CreateFromName ("SHA1")** -Methode aufrufen. Jede Methode garantiert nur, dass Sie ein Objekt zurückgibt, das den SHA1-Algorithmus implementiert. Sie müssen nicht jeden anzeigen Amen eines Algorithmus derselben Klasse in der Konfigurationsdatei zuordnen.  
  
 Eine Liste der Standardnamen und der Klassen, denen Sie zugeordnet sind, <xref:System.Security.Cryptography.CryptoConfig>finden Sie unter.  
  
## <a name="see-also"></a>Siehe auch

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
- [Konfigurieren kryptografischer Klassen](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
