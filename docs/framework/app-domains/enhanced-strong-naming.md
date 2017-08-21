---
title: Verbesserte starke Namen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 429a54340cef6d608692abd71311c012afe9a3d0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="enhanced-strong-naming"></a>Verbesserte starke Namen
Eine starke Namenssignatur ist ein Identitätsmechanismus in .NET Framework zum Identifizieren von Assemblys. In der Regel wird eine digitale Signatur mit öffentlichem Schlüssel verwendet, um die Integrität von Daten sicherzustellen, die von einem Absender (Signaturgeber) an einen Empfänger (Überprüfer) übergeben werden. Diese Signatur wird als eindeutige Identität für eine Assembly verwendet und gewährleistet, dass Verweise auf die Assembly nicht mehrdeutig sind. Die Assembly wird als Teil des Buildprozesses signiert und anschließend überprüft, wenn sie geladen wird.  
  
 Starke Namenssignaturen helfen, bösartige Parteien daran zu hindern, eine Assembly zu manipulieren und sie anschließend mit dem Schlüssel des ursprünglichen Signaturgebers neu zu signieren. Allerdings enthalten Schlüssel mit starkem Namen weder zuverlässige Informationen zum Herausgeber, noch enthalten sie eine Zertifikatshierarchie. Eine starke Namenssignatur garantiert nicht die Vertrauenswürdigkeit der Person, die die Assembly signiert hat, und gibt auch nicht an, ob diese Person ein legitimer Besitzer des Schlüssels war. Sie gibt nur an, dass der Besitzer des Schlüssels die Assembly signiert hat. Daher empfiehlt es sich nicht, eine starke Namenssignatur als Sicherheitsbestätigung für Code von Drittanbietern zu verwenden. Zur Authentifizierung von Code wird Microsoft Authenticode empfohlen.  
  
## <a name="limitations-of-conventional-strong-names"></a>Beschränkungen der konventionellen starken Namen  
 Die starke Benennungstechnologie, die in Versionen vor [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] verwendet wird, hat folgende Nachteile:  
  
-   Die Schlüssel werden ständig attackiert, und durch verbesserte Techniken und Hardware ist es einfacher, einen privaten Schlüssel von einem öffentlichen abzuleiten. Zum Schutz gegen Angriffe sind größere Schlüssel erforderlich. .NET Framework-Versionen vor [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bieten die Möglichkeit, mit einem beliebigen Größenschlüssel zu signieren (die Standardgröße ist 1024 Bit), das Signieren einer Assembly mit einem neuen Schlüssel bricht jedoch alle Binärdateien, die auf die ältere Identität der Assembly verweisen. Daher ist es extrem schwierig, die Größe eines Signaturschlüssels zu aktualisieren, wenn Sie Kompatibilität beibehalten möchten.  
  
-   Signierung mit starken Namen unterstützt nur den SHA-1-Algorithmus. Es wurde kürzlich festgestellt, dass SHA-1 für die Sicherung von Hashing-Anwendungen unzureichend ist. Daher ist ein stärkerer Algorithmus (SHA-256 oder höher) erforderlich. Es ist möglich, dass SHA-1 die FIPS-kompatible Position verliert, was zu Problemen für diejenigen führen würde, die sich entscheiden, nur FIPS-kompatible Software und Algorithmen zu verwenden.  
  
## <a name="advantages-of-enhanced-strong-names"></a>Vorteile von erweiterten starken Namen  
 Die Hauptvorteile von erweiterten starken Namen sind Kompatibilität mit bereits vorhandenen starken Namen und die Möglichkeit, zu beanspruchen, dass eine Identität einer anderen entspricht:  
  
-   Entwickler mit bereits vorhandenen signierten Assemblys können ihre Identitäten zu SHA-2-Algorithmen migrieren, wobei die Kompatibilität mit Assemblys, die auf alte Identitäten verweisen, beibehalten wird.  
  
-   Entwickler, die neue Assemblys erstellen und sich nicht mit vorhandenen starken Namenssignaturen befassen müssen, können die sichereren SHA-2-Algorithmen und die Assemblys wie gewohnt signieren.  
  
## <a name="using-enhanced-strong-names"></a>Verwenden von verbesserten starken Namen  
 Schlüssel mit starkem Namen bestehen aus einem Signaturschlüssel und einem Identitätsschlüssel. Die Assembly wird mit dem Signaturschlüssel signiert und durch den Identitätsschlüssel identifiziert. Vor [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] waren diese beiden Schlüssel identisch. Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bleibt der Identitätsschlüssel gleich wie in früheren .NET Framework-Versionen, der Signaturschlüssel wird jedoch durch einen stärkeren Hashalgorithmus verbessert. Außerdem wird der Signaturschlüssel mit dem Identitätsschlüssels signiert, um eine Gegensignatur zu erstellen.  
  
 Mithilfe des <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attributs können die Assemblymetadaten den bereits vorhandenen öffentlichen Schlüssel für die Assemblyidentität verwenden, wodurch alte Assemblyverweise weiterhin funktionieren.  Das <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attribut verwendet die Gegensignatur, um sicherzustellen, dass der Besitzer des neuen Signaturschlüssels auch der Besitzer des alten Identitätsschlüssels ist.  
  
### <a name="signing-with-sha-2-without-key-migration"></a>Signieren mit SHA-2, ohne Schlüsselmigration  
 Führen Sie die folgenden Befehle in einem Eingabeaufforderungsfenster aus, um eine Assembly zu signieren, ohne eine starke Namenssignatur zu migrieren:  
  
1.  Generieren Sie den neuen Identitätsschlüssels (falls erforderlich).  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  Extrahieren Sie den öffentlichen Identitätsschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  Führen Sie eine verzögerte Signierung der Assembly mit der öffentlichen Identitätsschlüsseldatei durch.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  Signieren Sie die Assembly mit dem vollständigen Identitätsschlüsselpaar erneut.  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a>Signieren mit SHA-2, mit Schlüsselmigration  
 Führen Sie die folgenden Befehle in einem Eingabeaufforderungsfenster aus, um eine Assembly mit einer migrierten starken Namenssignatur zu signieren.  
  
1.  Generieren Sie ein Identitäts- und Signaturschlüsselpaar (falls erforderlich).  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  Extrahieren Sie den öffentlichen Signaturschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  Extrahieren Sie den öffentlichen Identitätsschlüssel, der den Hashalgorithmus bestimmt, der eine Gegensignatur generiert.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  Generieren Sie die Parameter für ein <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attribut, und fügen Sie das Attribut an die Assembly an.  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  Führen Sie eine verzögerte Signierung der Assembly mit dem öffentlichen Identitätsschlüssel durch.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6.  Führen Sie eine vollständige Signatur der Assembly mit dem Signaturschlüsselpaar durch.  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

