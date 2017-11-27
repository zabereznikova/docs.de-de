---
title: Zuordnen von Algorithmennamen zu kryptografischen Klassen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e59b2551545b8b70bcb54a5d43d041c44579b786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>Zuordnen von Algorithmennamen zu kryptografischen Klassen
Es gibt vier Möglichkeiten, die ein Entwickler ein Kryptografie-Objekt mithilfe erstellen kann der [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   Erstellen Sie ein Objekt mithilfe der **neue** Operator.  
  
-   Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der **erstellen** Methode in der abstrakten Klasse für diesen Algorithmus.  
  
-   Erstellen Sie ein Objekt, das einen bestimmten kryptografischen Algorithmus, durch Aufrufen implementiert der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> Methode.  
  
-   Erstellen Sie ein Objekt, das eine Klasse kryptografischer Algorithmen (z. B. symmetrische Blockchiffre), durch Aufrufen implementiert der **erstellen** Methode in der abstrakten Klasse für diesen Typ des-Algorithmus (z. B. <xref:System.Security.Cryptography.SymmetricAlgorithm>).  
  
 Nehmen wir beispielsweise an, dass ein Entwickler möchte den SHA1-Hash einer Reihe von Bytes zu berechnen. Die <xref:System.Security.Cryptography> -Namespace enthält zwei Implementierungen von den SHA1-Algorithmus, eine rein verwaltete Implementierung und die CryptoAPI umschließt. Der Entwickler die Möglichkeit, eine bestimmte SHA1-Implementierung instanziieren (z. B. die <xref:System.Security.Cryptography.SHA1Managed>) durch Aufrufen der **neue** Operator. Wenn es nicht, welche Klasse die common Language Runtime lädt ausschlaggebend, solange die Klasse des SHA1-Hash-Algorithmus implementiert, der Entwickler kann jedoch erstellen ein Objekt durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> Methode. Diese Methode ruft **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1") auf**, muss die eine Implementierung des SHA1-Hashalgorithmus zurückgeben.  
  
 Der Entwickler kann auch aufrufen **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** da standardmäßig Kryptografiekonfiguration Kurznamen für die Algorithmen, die im Lieferumfang von .NET Framework enthält.  
  
 Wenn es nicht ausschlaggebend, welche Hash-Algorithmus verwendet wird, kann der Entwickler rufen die <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> Methode, die ein Objekt zurückgibt, die eine hashing Transformation implementiert.  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>Zuordnen von Algorithmennamen in Konfigurationsdateien  
 Standardmäßig gibt die Runtime eine <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> Objekt für alle vier Szenarien. Ein Computeradministrator kann jedoch den Typ des Objekts ändern, die die Methoden in den letzten beiden Szenarien zurückgeben. Zu diesem Zweck müssen Sie die Klasse ein angezeigte Algorithmusnamen zuordnen, die Sie in der Computerkonfigurationsdatei ("Machine.config") verwenden möchten.  
  
 Im folgende Beispiel wird gezeigt, wie die Common Language Runtime zu konfigurieren, damit **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, und  **System.Security.Cryptography.HashAlgorithm.Create** Zurückgeben einer `MySHA1HashClass` Objekt.  
  
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
  
 Sie können angeben, den Namen des Attributs in der [< CryptoClass\> Element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (im vorherige Beispiel benennt das Attribut `MySHA1Hash`). Der Wert des Attributs in der  **\<CryptoClass >** Element ist eine Zeichenfolge, die common Language Runtime verwendet die Klasse nicht gefunden. Sie können eine beliebige Zeichenfolge, die im angegebenen Anforderungen erfüllt [angeben vollständig gekennzeichneter Typnamen](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).  
  
 Viele Algorithmusnamen können auf die gleiche Klasse zugeordnet werden. Die [ \<NameEntry >-Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) einen benutzerfreundlichen Algorithmusname eine Klasse zugeordnet. Die **Namen** Attribut kann entweder eine Zeichenfolge, die verwendet wird, beim Aufrufen der **System.Security.Cryptography.CryptoConfig.CreateFromName** -Methode oder der Name einer abstrakten kryptografischen Klasse in der <xref:System.Security.Cryptography> Namespace. Der Wert von der **Klasse** -Attribut ist der Name des Attributs in der  **\<CryptoClass >** Element.  
  
> [!NOTE]
>  Sie erhalten einen SHA1-Algorithmus durch Aufrufen der <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> oder **Security.CryptoConfig.CreateFromName("SHA1")** Methode. Jede Methode ist, gewährleistet lediglich, dass ein Objekt zurückgegeben wird, die den SHA1-Algorithmus implementiert. Sie müssen nicht jeden Anzeigenamen eines Algorithmus auf die gleiche Klasse in der Konfigurationsdatei zuordnen.  
  
 Eine Liste der Standardnamen und die Klassen, denen sie sind zugeordnet, finden Sie unter <xref:System.Security.Cryptography.CryptoConfig>.  
  
## <a name="see-also"></a>Siehe auch  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 [Konfigurieren kryptografischer Klassen](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
