---
title: ICLRStrongName-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRStrongName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName
helpviewer_keywords:
- ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type:
- apiref
ms.openlocfilehash: 4f774915cdbb12b13fa334db37c8e0fa2a7e5829
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135141"
---
# <a name="iclrstrongname-interface"></a>ICLRStrongName-Schnittstelle
Stellt grundlegende globale statische Funktionen zum Signieren von Assemblys mit starken Namen bereit. Alle `ICLRStrongName` Methoden geben Standard-com-HRESULTs zurück.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetHashFromAssemblyFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)|Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.|  
|[GetHashFromAssemblyFileW-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)|Ruft einen Hash der als Unicode-Zeichenfolge angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.|  
|[GetHashFromBlob-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)|Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.|  
|[GetHashFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)|Generiert einen Hashwert für den Inhalt der angegebenen Datei.|  
|[GetHashFromFileW-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)|Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.|  
|[GetHashFromHandle-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)|Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.|  
|[StrongNameCompareAssemblies-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)|Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.|  
|[StrongNameFreeBuffer-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Gibt Arbeitsspeicher frei, der mit einem vorherigen Aufruf einer starken Namens Methode wie [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)oder [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)zugeordnet wurde.|  
|[StrongNameGetBlob-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)|Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.|  
|[StrongNameGetBlobFromImage-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)|Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.|  
|[StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)|Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab.|  
|[StrongNameHashSize-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)|Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.|  
|[StrongNameKeyDelete-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)|Löscht den angegebenen Schlüsselcontainer.|  
|[StrongNameKeyGen-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)|Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.|  
|[StrongNameKeyGenEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)|Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung von starken Namen.|  
|[StrongNameKeyInstall-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)|Importiert ein öffentliches/privates Schlüsselpaar in einen Container.|  
|[StrongNameSignatureGeneration-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)|Generiert eine Signatur mit starkem Namen für die angegebene Assembly.|  
|[StrongNameSignatureGenerationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)|Generiert eine Signatur mit starkem Namen für die angegebene Assembly basierend auf den angegebenen Flags.|  
|[StrongNameSignatureSize-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)|Gibt die Größe der Signatur mit starkem Namen zurück.|  
|[StrongNameSignatureVerification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)|Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.|  
|[StrongNameSignatureVerificationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)|Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.|  
|[StrongNameSignatureVerificationFromImage-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.|  
|[StrongNameTokenFromAssembly-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)|Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.|  
|[StrongNameTokenFromAssemblyEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)|Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück.|  
|[StrongNameTokenFromPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)|Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine Instanz des `ICLRStrongName` abrufen, indem Sie die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode mithilfe von `CLSID_CLRStrongName` und `IID_ICLRStrongName` als Parameter aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
