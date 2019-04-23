---
title: Verbesserte starke Namen
ms.date: 03/30/2017
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cbda9c160b99bf5648c670a67d39b245f031645
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319871"
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
  
1. Generieren Sie den neuen Identitätsschlüssels (falls erforderlich).  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2. Extrahieren Sie den öffentlichen Identitätsschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3. Führen Sie eine verzögerte Signierung der Assembly mit der öffentlichen Identitätsschlüsseldatei durch.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4. Signieren Sie die Assembly mit dem vollständigen Identitätsschlüsselpaar erneut.  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a>Signieren mit SHA-2, mit Schlüsselmigration  
 Führen Sie die folgenden Befehle in einem Eingabeaufforderungsfenster aus, um eine Assembly mit einer migrierten starken Namenssignatur zu signieren.  
  
1. Generieren Sie ein Identitäts- und Signaturschlüsselpaar (falls erforderlich).  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2. Extrahieren Sie den öffentlichen Signaturschlüssel, und geben Sie an, dass ein SHA-2-Algorithmus beim Signieren mit diesem Schlüssel verwendet werden soll.  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3. Extrahieren Sie den öffentlichen Identitätsschlüssel, der den Hashalgorithmus bestimmt, der eine Gegensignatur generiert.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4. Generieren Sie die Parameter für ein <xref:System.Reflection.AssemblySignatureKeyAttribute>-Attribut, und fügen Sie das Attribut an die Assembly an.  
  
    ```  
    sn -a IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  

    Dadurch wird eine Ausgabe erzeugt, die der Folgenden ähnelt:

    ```
    Information for key migration attribute.
    (System.Reflection.AssemblySignatureKeyAttribute):
    publicKey=
    002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519
    d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936
    e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b4
    3893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a3
    4d153cdd

    counterSignature=
    e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91eb
    e1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8
    ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3
    ae5fec2c682e57b7442738
    ```

    Diese Ausgabe kann dann in ein AssemblySignatureKeyAttribute transformiert werden.

    ```
    [assembly:System.Reflection.AssemblySignatureKeyAttribute(
    "002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b43893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a34d153cdd",
    "e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91ebe1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3ae5fec2c682e57b7442738"
    )]
    ```
  
5. Führen Sie eine verzögerte Signierung der Assembly mit dem öffentlichen Identitätsschlüssel durch.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6. Führen Sie eine vollständige Signatur der Assembly mit dem Signaturschlüsselpaar durch.  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
