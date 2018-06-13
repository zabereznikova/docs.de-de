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
ms.openlocfilehash: 6c397a325edb49e3f10a46b242888b8d138957af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462376"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Verwenden von starken Namen (Referenz zur nicht verwalteten API)
Die API für starke Namen kann ein Client zum Verwalten der Signierung für Assemblys mit starken Namens.  
  
 Beim Signieren einer Assembly mit einem starken Namen wird der Datei, die das Assemblymanifest enthält, eine Verschlüsselung mit einem öffentlichen Schlüssel hinzugefügt. Signieren mit starkem Namen hilft Überprüfen der Eindeutigkeit der Namen, verhindert Vortäuschen von Namen und stellt Aufrufern eine eindeutige Identität bereit, wenn ein Verweis aufgelöst wird. Allerdings ist keine Maß an Vertrauenswürdigkeit mit einem starken Namen verknüpft.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Starke Namen von globalen statischen Funktionen](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 Beschreibt die nicht verwalteten globalen statischen Funktionen, die die API für starke Namen verwendet.  
  
> [!NOTE]
>  All diese Funktionen sind veraltet beginnend mit der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Empfohlene Alternativen finden Sie unter der [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) Schnittstelle.  
  
 [GetHashFromAssemblyFile-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Ruft einen Hash der angegebenen Assemblydatei, die mithilfe des angegebenen Hashalgorithmus ab. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromAssemblyFileW-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Ruft einen Hash der Assemblydatei, angegeben als Unicode-Zeichenfolge unter Verwendung des angegebenen Hashalgorithmus ab. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromBlob-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Ruft einen Hash der Assembly an der angegebenen Speicheradresse, die mithilfe des angegebenen Hashalgorithmus ab. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFile-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Generiert einen Hash des Inhalts der angegebenen Datei.  Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFileW-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Generiert einen Hash des Inhalts der Datei durch eine Unicode-Zeichenfolge angegeben. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromHandle-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Generiert einen Hash des Inhalts der Datei mit das angegebene Dateihandle mithilfe des angegebenen Hashalgorithmus.  Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameCompareAssemblies-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Bestimmt, ob zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameErrorInfo-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.  
  
 [StrongNameFreeBuffer-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Gibt den Arbeitsspeicher, der mit einem vorherigen Aufruf einer Funktion mit starkem Namen wie z. B. frei [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), oder [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlob-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse an. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlobFromImage-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Ruft eine binäre Darstellung des Assemblyabbilds an der angegebenen Speicheradresse. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetPublicKey-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Ruft den öffentlichen Schlüssel aus einem Schlüsselpaar mit privaten und öffentlichen ab. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameHashSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Ruft die Größe des Puffers für einen Hash, der mithilfe des angegebenen Hashalgorithmus erforderlich sind.  Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyDelete-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Löscht den angegebenen Schlüsselcontainer. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGen-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Erstellt ein neues öffentliches/privates Schlüsselpaar für starke Namen verwenden.  Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGenEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung der starken Namen an. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyInstall-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importiert ein öffentliches/privates Schlüsselpaar in einen Container.  Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGeneration-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Generiert eine starke Namenssignatur für die angegebene Assembly an.   Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGenerationEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Generiert eine starke Namenssignatur für die angegebene Assembly, die basierend auf den angegebenen Flags.    Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Gibt die Größe der Signatur des starken Namens. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerification-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine starke Namenssignatur enthält, die gemäß den angegebenen Flags überprüft wird. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine starke Namenssignatur enthält.  Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationFromImage-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Überprüft, ob eine Assembly, die bereits in den Arbeitsspeicher zugeordnet wurde für den zugehörigen öffentlichen Schlüssel gültig ist. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssembly-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei an.  Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssemblyEx-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromPublicKey-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Ruft ein Token, das einen öffentlichen Schlüssel darstellt. Veraltete ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Starke Benennung-Struktur](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 Beschreibt die nicht verwaltete Struktur, die die API für starke Namen verwendet, zum Verwalten der Signierung für Assemblys mit starken Namens...  
  
 [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im Binärformat.  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [Referenz zur nicht verwalteten API](../../../../docs/framework/unmanaged-api/index.md)
