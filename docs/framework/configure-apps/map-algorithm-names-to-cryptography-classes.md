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
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Zuordnen von Algorithmennamen zu kryptografischen Klassen
Es gibt vier Möglichkeiten, wie ein Entwickler ein Kryptografieobjekt mithilfe des Windows SDK erstellen kann:  
  
- Erstellen Sie ein-Objekt, indem Sie den **New** -Operator verwenden.  
  
- Erstellen Sie ein Objekt, das einen bestimmten Kryptografiealgorithmus durch Aufrufen der **Create** -Methode für die abstrakte Klasse für diesen Algorithmus implementiert.  
  
- Erstellen Sie ein Objekt, das einen bestimmten Kryptografiealgorithmus implementiert, indem Sie die- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode aufrufen.  
  
- Erstellen Sie ein Objekt, das eine Klasse kryptografischer Algorithmen implementiert (z. b. eine symmetrische Blockchiffre), indem Sie die **Create** -Methode für die abstrakte Klasse für diesen Algorithmustyp aufrufen (z <xref:System.Security.Cryptography.SymmetricAlgorithm> . b.).  
  
 Nehmen wir beispielsweise an, ein Entwickler möchte den SHA1-Hash eines Satzes von Bytes berechnen. Der- <xref:System.Security.Cryptography> Namespace enthält zwei Implementierungen des SHA1-Algorithmus, eine rein verwaltete Implementierung und eine, die CryptoAPI umschließt. Der Entwickler kann eine bestimmte SHA1-Implementierung (z. b. <xref:System.Security.Cryptography.SHA1Managed> ) durch Aufrufen des **New** -Operators instanziieren. Wenn es jedoch keine Rolle spielt, welche Klasse das Common Language Runtime lädt, solange die Klasse den SHA1-Hash Algorithmus implementiert, kann der Entwickler ein Objekt durch Aufrufen der- <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode erstellen. Diese Methode ruft **System. Security. Cryptography. CryptoConfig. kreatefromname ("System. Security. Cryptography. SHA1")** auf, der eine Implementierung des SHA1-Hash Algorithmus zurückgeben muss.  
  
 Der Entwickler kann auch **System. Security. Kryptografie. CryptoConfig. kreatefromname ("SHA1")** aufrufen, da die Kryptografiekonfiguration standardmäßig Kurznamen für die Algorithmen enthält, die im .NET Framework ausgeliefert werden.  
  
 Wenn es keine Rolle spielt, welcher Hash Algorithmus verwendet wird, kann der Entwickler die-Methode aufzurufen <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> , die ein Objekt zurückgibt, das eine Hash Transformation implementiert.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Mapping von Algorithmusnamen in Konfigurationsdateien  
 Standardmäßig gibt die Laufzeit ein- <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> Objekt für alle vier Szenarien zurück. Ein Computer Administrator kann jedoch den Objekttyp ändern, den die Methoden in den letzten beiden Szenarien zurückgegeben haben. Zu diesem Zweck müssen Sie der Klasse, die Sie in der Computer Konfigurationsdatei (Machine. config) verwenden möchten, einen anzeigen Amen für den Algorithmus zuordnen.  
  
 Im folgenden Beispiel wird gezeigt, wie die Laufzeit so konfiguriert wird, dass **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. kreatefromname ("SHA1")** und **System. Security. Cryptography. HashAlgorithm. Create** ein-Objekt zurückgeben `MySHA1HashClass` .  
  
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
  
 Sie können den Namen des Attributs im [<CryptoClass- \> Element](./file-schema/cryptography/cryptoclass-element.md) angeben (im vorherigen Beispiel wird das-Attribut benannt `MySHA1Hash` ). Der Wert des-Attributs im- **\<cryptoClass>** Element ist eine Zeichenfolge, die der Common Language Runtime verwendet, um die-Klasse zu suchen. Sie können jede beliebige Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.  
  
 Viele Algorithmusnamen können derselben Klasse zugeordnet werden. Das- [ \<nameEntry> Element](./file-schema/cryptography/nameentry-element.md) ordnet eine Klasse einem benutzerfreundlichen Algorithmusnamen zu. Das **Name** -Attribut kann entweder eine Zeichenfolge sein, die beim Aufrufen der **System. Security. Kryptografie. CryptoConfig. CreateFromName** -Methode oder der Name einer abstrakten Kryptografieklasse im- <xref:System.Security.Cryptography> Namespace verwendet wird. Der Wert des **Class** -Attributs ist der Name des Attributs im- **\<cryptoClass>** Element.  
  
> [!NOTE]
> Sie können einen SHA1-Algorithmus abrufen, indem Sie die- <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode oder die **Security. CryptoConfig. CreateFromName ("SHA1")** -Methode aufrufen. Jede Methode garantiert nur, dass Sie ein Objekt zurückgibt, das den SHA1-Algorithmus implementiert. Sie müssen nicht jeden anzeigen Amen eines Algorithmus derselben Klasse in der Konfigurationsdatei zuordnen.  
  
 Eine Liste der Standardnamen und der Klassen, denen Sie zugeordnet sind, finden Sie unter <xref:System.Security.Cryptography.CryptoConfig> .  
  
## <a name="see-also"></a>Weitere Informationen

- [Kryptografiedienste](../../standard/security/cryptographic-services.md)
- [Konfigurieren kryptografischer Klassen](configure-cryptography-classes.md)
