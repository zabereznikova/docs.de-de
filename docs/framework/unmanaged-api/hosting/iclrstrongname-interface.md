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
ms.openlocfilehash: 691cc3cf4ec8d036a4de04247f243d99daa887d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733632"
---
# <a name="iclrstrongname-interface"></a>ICLRStrongName-Schnittstelle

Stellt grundlegende globale statische Funktionen zum Signieren von Assemblys mit starken Namen bereit. Alle `ICLRStrongName` Methoden geben Standard-com-HRESULTs zurück.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetHashFromAssemblyFile-Methode](iclrstrongname-gethashfromassemblyfile-method.md)|Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.|  
|[GetHashFromAssemblyFileW-Methode](iclrstrongname-gethashfromassemblyfilew-method.md)|Ruft einen Hash der als Unicode-Zeichenfolge angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.|  
|[GetHashFromBlob-Methode](iclrstrongname-gethashfromblob-method.md)|Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.|  
|[GetHashFromFile-Methode](iclrstrongname-gethashfromfile-method.md)|Generiert einen Hashwert für den Inhalt der angegebenen Datei.|  
|[GetHashFromFileW-Methode](iclrstrongname-gethashfromfilew-method.md)|Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.|  
|[GetHashFromHandle-Methode](iclrstrongname-gethashfromhandle-method.md)|Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.|  
|[StrongNameCompareAssemblies-Methode](iclrstrongname-strongnamecompareassemblies-method.md)|Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.|  
|[StrongNameFreeBuffer-Methode](iclrstrongname-strongnamefreebuffer-method.md)|Gibt Arbeitsspeicher frei, der mit einem vorherigen Aufruf einer starken Namens Methode wie [StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)oder [StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md)zugeordnet wurde.|  
|[StrongNameGetBlob-Methode](iclrstrongname-strongnamegetblob-method.md)|Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.|  
|[StrongNameGetBlobFromImage-Methode](iclrstrongname-strongnamegetblobfromimage-method.md)|Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.|  
|[StrongNameGetPublicKey-Methode](iclrstrongname-strongnamegetpublickey-method.md)|Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab.|  
|[StrongNameHashSize-Methode](iclrstrongname-strongnamehashsize-method.md)|Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.|  
|[StrongNameKeyDelete-Methode](iclrstrongname-strongnamekeydelete-method.md)|Löscht den angegebenen Schlüsselcontainer.|  
|[StrongNameKeyGen-Methode](iclrstrongname-strongnamekeygen-method.md)|Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.|  
|[StrongNameKeyGenEx-Methode](iclrstrongname-strongnamekeygenex-method.md)|Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung von starken Namen.|  
|[StrongNameKeyInstall-Methode](iclrstrongname-strongnamekeyinstall-method.md)|Importiert ein öffentliches/privates Schlüsselpaar in einen Container.|  
|[StrongNameSignatureGeneration-Methode](iclrstrongname-strongnamesignaturegeneration-method.md)|Generiert eine Signatur mit starkem Namen für die angegebene Assembly.|  
|[StrongNameSignatureGenerationEx-Methode](iclrstrongname-strongnamesignaturegenerationex-method.md)|Generiert eine Signatur mit starkem Namen für die angegebene Assembly basierend auf den angegebenen Flags.|  
|[StrongNameSignatureSize-Methode](iclrstrongname-strongnamesignaturesize-method.md)|Gibt die Größe der Signatur mit starkem Namen zurück.|  
|[StrongNameSignatureVerification-Methode](iclrstrongname-strongnamesignatureverification-method.md)|Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.|  
|[StrongNameSignatureVerificationEx-Methode](iclrstrongname-strongnamesignatureverificationex-method.md)|Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.|  
|[StrongNameSignatureVerificationFromImage-Methode](iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.|  
|[StrongNameTokenFromAssembly-Methode](iclrstrongname-strongnametokenfromassembly-method.md)|Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.|  
|[StrongNameTokenFromAssemblyEx-Methode](iclrstrongname-strongnametokenfromassemblyex-method.md)|Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück.|  
|[StrongNameTokenFromPublicKey-Methode](iclrstrongname-strongnametokenfrompublickey-method.md)|Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.|  
  
## <a name="remarks"></a>Hinweise  

 Sie können eine Instanz von abrufen, `ICLRStrongName` indem Sie die [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) -Methode mithilfe von `CLSID_CLRStrongName` und `IID_ICLRStrongName` als Parameter aufrufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
