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
ms.openlocfilehash: cd57cc7bbe39b042e11d0dad3fd54373bcaae98b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076512"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Zuordnen von Algorithmennamen zu kryptografischen Klassen
Es gibt vier Möglichkeiten, die ein Entwickler ein Kryptografie mithilfe erstellen kann der [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Erstellen Sie ein Objekt mithilfe der **neue** Operator.  
  
-   Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der **erstellen** Methode für die abstrakte Klasse für diesen Algorithmus.  
  
-   Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode.  
  
-   Erstellen Sie ein Objekt, das implementiert, eine Klasse von kryptografischen Algorithmen (z. B. eine Verschlüsselung symmetrischer Blöcke) durch Aufrufen der **erstellen** Methode für die abstrakte Klasse für diesen Typ des-Algorithmus (z. B. <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Nehmen wir beispielsweise an, dass ein Entwickler möchte, um den SHA1-Hash einer Reihe von Bytes zu berechnen. Die <xref:System.Security.Cryptography> -Namespace enthält zwei Implementierungen von SHA1-Algorithmus, eine rein verwaltete Implementierungen und diejenige, die CryptoAPI umschließt. Entwickler kann auch eine bestimmte Implementierung des SHA1 instanziieren (z. B. die <xref:System.Security.Cryptography.SHA1Managed>) durch Aufrufen der **neue** Operator. Jedoch wenn es keine, welche Klasse die common Language Runtime lädt Rolle, solange die Klasse des SHA1-Hash-Algorithmus implementiert, der Entwickler kann erstellen ein Objekt durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode. Diese Methode ruft **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1") auf**, womit muss eine Implementierung des SHA1-Hashalgorithmus zurückgegeben.  
  
 Entwickler kann auch aufrufen, **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** daran, dass standardmäßig die Kryptografiekonfiguration kurze Namen für die Algorithmen, die im Lieferumfang von .NET Framework enthält.  
  
 Wenn es keine Rolle spielt die Hashalgorithmus verwendet wird, kann der Entwickler Aufrufen der <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> Methode, die ein Objekt zurückgibt, die eine Transformation Hashalgorithmus implementiert.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Zuordnen von Algorithmennamen in Konfigurationsdateien  
 Standardmäßig gibt die Runtime eine <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> -Objekt für alle vier Szenarien. Ein Computeradministrator kann jedoch den Typ des Objekts ändern, die die Methoden in den letzten beiden Szenarien zurückgeben. Zu diesem Zweck müssen Sie einen Namen für die Anzeigenamen von Algorithmen für die Klasse zuordnen, die Sie in der Computerkonfigurationsdatei (Machine.config) verwenden möchten.  
  
 Das folgende Beispiel zeigt, wie die Laufzeit so konfiguriert, damit **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, und  **System.Security.Cryptography.HashAlgorithm.Create** Zurückgeben einer `MySHA1HashClass` Objekt.  
  
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
  
 Sie können angeben, den Namen des Attributs in der [< CryptoClass\> Element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (im vorherige Beispiel benennt das Attribut `MySHA1Hash`). Der Wert des Attributs in der  **\<CryptoClass >** Element ist eine Zeichenfolge, die die common Language Runtime verwendet wird, um die Klasse zu finden. Sie können eine beliebige Zeichenfolge, die die in angegebenen Anforderungen erfüllt [angeben vollständig gekennzeichneter Typnamen](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Viele können Algorithmen die gleiche Klasse zugeordnet. Die [ \<NameEntry >-Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) einen Anzeigenamen von Algorithmusnamen eine Klasse zugeordnet. Die **Namen** Attribut kann entweder eine Zeichenfolge, die verwendet wird, beim Aufrufen von sein der **System.Security.Cryptography.CryptoConfig.CreateFromName** Methode oder den Namen einer abstrakten kryptografischen Klasse in der <xref:System.Security.Cryptography> Namespace. Der Wert des der **Klasse** Attribut ist der Name des Attributs in der  **\<CryptoClass >** Element.  
  
> [!NOTE]
>  Sie erhalten einen SHA1-Algorithmus durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> oder **Security.CryptoConfig.CreateFromName("SHA1")** Methode. Jede Methode garantiert nur an, dass es sich um ein Objekt zurückgibt, die den SHA1-Algorithmus implementiert. Sie müssen nicht jede Anzeigenamen eines Algorithmus auf dieselbe Klasse in der Konfigurationsdatei zuordnen.  
  
 Eine Liste der Namen für Standardwerte und die Klassen, die sie sind zugeordnet, finden Sie unter <xref:System.Security.Cryptography.CryptoConfig>.  
  
## <a name="see-also"></a>Siehe auch  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 [Konfigurieren kryptografischer Klassen](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
