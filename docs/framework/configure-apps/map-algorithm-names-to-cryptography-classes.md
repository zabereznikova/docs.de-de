---
title: "Zuordnen von Algorithmennamen zu kryptografischen Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Kryptografische Algorithmen"
  - "Kryptografie, Zuordnen von Algorithmennamen"
  - "Zuordnen von Algorithmennamen"
  - "Namen [.NET Framework], Algorithmuszuordnung"
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Zuordnen von Algorithmennamen zu kryptografischen Klassen
Mit [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] können Entwickler kryptografische Objekte auf vier Arten erstellen:  
  
-   Erstellen eines Objekts durch Verwenden des Operators **new**.  
  
-   Erstellen eines Objekts, das einen bestimmten kryptografischen Algorithmus implementiert, durch Aufrufen der **Create**\-Methode in der abstrakten Klasse dieses Algorithmus.  
  
-   Erstellen eines Objekts, das einen bestimmten kryptografischen Algorithmus implementiert, durch Aufrufen der [System.Security.Cryptography.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic)\-Methode.  
  
-   Erstellen eines Objekts, das eine Klasse kryptografischer Algorithmen implementiert \(z. B. symmetrische Blockchiffre\) durch Aufrufen der **Create\-**Methode in der abstrakten Klasse dieses Algorithmustyps \(z. B. <xref:System.Security.Cryptography.SymmetricAlgorithm>\).  
  
 Angenommen, ein Entwickler möchte den SHA1\-Hash eines Bytesatzes berechnen.  Der <xref:System.Security.Cryptography>\-Namespace enthält zwei Implementierungen des SHA1\-Algorithmus, eine rein verwaltete Implementierung und eine, die CryptoAPI umschließt.  Der Entwickler kann durch Aufrufen des Operators **new** eine bestimmte SHA1\-Implementierung instanziieren \(z. B. die [SHA1Managed\-Klasse](frlrfSystemSecurityCryptographySHA1ManagedClassTopic)\).  Es spielt jedoch keine Rolle, welche Klasse die Common Language Runtime lädt. Solange die Klasse den SHA1\-Hashalgorithmus implementiert, kann ein Objekt durch Aufrufen der [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic)\-Methode erstellt werden.  Diese Methode ruft **System.Security.Cryptography.CryptoConfig.CreateFromName\("System.Security.Cryptography.SHA1"\)** auf, wodurch eine Implementierung des SHA1\-Hashalgorithmus zurückgegeben werden muss.  
  
 Der Entwickler kann auch **System.Security.Cryptography.CryptoConfig.CreateFromName\("SHA1"\)** aufrufen, weil Kryptografiekonfigurationssysteme standardmäßig Kurznamen für die in .NET Framework mitgelieferten Algorithmen enthalten.  
  
 Wenn es nicht darauf ankommt, welcher Hashalgorithmus verwendet wird, kann durch Aufruf der [System.Security.Cryptography.HashAlgorithm.Create](frlrfSystemSecurityCryptographyHashAlgorithmClassCreateTopic)\-Methode ein Objekt zurückgegeben werden, das eine Hashtransformation implementiert.  
  
## Zuordnen von Algorithmusnamen zu Konfigurationsdateien  
 Standardmäßig gibt die Common Language Runtime ein [System.Security.Cryptography.SHA1CryptoServiceProvider\-Klassenobjekt](frlrfSystemSecurityCryptographySHA1CryptoServiceProviderClassTopic) für alle vier Szenarien zurück.  Ein Administrator kann jedoch den Objekttyp ändern, den die Methoden in den beiden letzten Szenarien zurückgeben.  Dazu muss ein angezeigter Algorithmusname der Klasse zugeordnet werden, die Sie in der Konfigurationsdatei des Computers \(Machine.config\) verwenden möchten.  
  
 Im folgenden Beispiel wird dargestellt, wie die Common Language Runtime so konfiguriert wird, dass **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName\("SHA1"\)** und **System.Security.Cryptography.HashAlgorithm.Create** ein `MySHA1HashClass`\-Objekt zurückgeben.  
  
```  
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
  
 Sie können den Namen des Attributs im [\<cryptoClass\>\-Element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) angeben \(im vorigen Beispiel heißt das Attribut `MySHA1Hash`\).  Der Wert des Attributs im **\<cryptoClass\>**\-Element ist eine Zeichenfolge mit der die Common Language Runtime, die Klasse zu finden.  Sie können jede Zeichenfolge verwenden, die die unter [Angeben vollständig gekennzeichneter Typnamen](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) aufgeführten Anforderungen erfüllt.  
  
 Viele Algorithmusnamen können der gleichen Klasse zugeordnet sein.  Das [\<nameEntry\>\-Element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) ordnet eine Klasse einem angezeigten Algorithmusnamen zu.  Das **name**\-Attribut kann entweder eine Zeichenfolge sein, die beim Aufrufen der **System.Security.Cryptography.CryptoConfig.CreateFromName**\-Methode verwendet wird, oder der Name einer abstrakten kryptografischen Klasse im <xref:System.Security.Cryptography>\-Namespace.  Der Wert des **Klasse**\-Attributs ist der Name des Attributs im **\<cryptoClass\>**\-Element.  
  
> [!NOTE]
>  Sie können einen SHA1\-Algorithmus durch Aufruf der [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic)\-Methode oder der **Security.CryptoConfig.CreateFromName\("SHA1"\)**\-Methode erhalten.  Durch jede dieser Methoden wird lediglich gewährleistet, dass ein Objekt zurückgegeben wird, das den SHA1\-Algorithmus implementiert.  Es ist nicht erforderlich, jeden angezeigten Algorithmusnamen derselben Klasse in der Konfigurationsdatei zuzuordnen.  
  
 Eine Liste mit Standardnamen und den zugeordneten Klassen finden Sie unter der [CryptoConfig\-Klasse](frlrfSystemSecurityCryptographyCryptoConfigClassTopic).  
  
## Siehe auch  
 [Kryptografische Dienste](../../../docs/standard/security/cryptographic-services.md)   
 [Konfigurieren kryptografischer Klassen](../../../docs/framework/configure-apps/configure-cryptography-classes.md)