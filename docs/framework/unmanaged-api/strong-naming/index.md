---
title: Verwenden von starken Namen (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32e74a76b6b1bedee4efc5715d0710c8efce2455
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120756"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Verwenden von starken Namen (Referenz zur nicht verwalteten API)
Die API für starke Namen ermöglicht es einem Client, die starke Namenssignierung für Assemblys zu verwalten.  
  
 Beim Signieren einer Assembly mit einem starken Namen wird der Datei, die das Assemblymanifest enthält, eine Verschlüsselung mit einem öffentlichen Schlüssel hinzugefügt. Das Signieren mit starkem Namen gewährleistet die Eindeutigkeit der Namen, verhindert das Vortäuschen von Namen (Spoofing) und stellt Aufrufern beim Auflösen eines Verweises eine eindeutige Identität bereit. Mit einem starken Namen ist jedoch keine Vertrauensebene verknüpft.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
> [!NOTE]
>  Alle diese Funktionen sind veraltet, beginnend mit [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Empfohlene Alternativen finden Sie in der [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)-Schnittstelle.  
  
 [GetHashFromAssemblyFile-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromAssemblyFileW-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Ruft einen Hash der als Unicode-Zeichenfolge angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromBlob-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFile-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Generiert einen Hashwert für den Inhalt der angegebenen Datei.  Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFileW-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromHandle-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.  Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameCompareAssemblies-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameErrorInfo-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.  
  
 [StrongNameFreeBuffer-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Gibt Speicher frei, der bei einem vorherigen Aufruf einer Funktion für starke Namen wie [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) oder [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md) zugewiesen wurde.   Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlob-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlobFromImage-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetPublicKey-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameHashSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.  Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyDelete-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Löscht den angegebenen Schlüsselcontainer. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGen-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.  Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGenEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung von starken Namen. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyInstall-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importiert ein öffentliches/privates Schlüsselpaar in einen Container.  Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGeneration-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Generiert eine Signatur mit starkem Namen für die angegebene Assembly.   Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGenerationEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Generiert eine Signatur mit starkem Namen für die angegebene Assembly basierend auf den angegebenen Flags.    Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Gibt die Größe der Signatur mit starkem Namen zurück. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerification-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.  Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationFromImage-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssembly-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.  Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssemblyEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromPublicKey-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt. Veraltet ab [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im binären Format dar.  
  
## <a name="see-also"></a>Siehe auch

- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Referenz zur nicht verwalteten API](../../../../docs/framework/unmanaged-api/index.md)
