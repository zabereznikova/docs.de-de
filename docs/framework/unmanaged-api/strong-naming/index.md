---
title: Verwenden von starken Namen (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
ms.openlocfilehash: 7e431f3a41fadb7247f20d7ab9bb9120e827b0cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732293"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Verwenden von starken Namen (Referenz zur nicht verwalteten API)

Die API für starke Namen ermöglicht es einem Client, die starke Namenssignierung für Assemblys zu verwalten.  
  
 Beim Signieren einer Assembly mit einem starken Namen wird der Datei, die das Assemblymanifest enthält, eine Verschlüsselung mit einem öffentlichen Schlüssel hinzugefügt. Das Signieren mit starkem Namen gewährleistet die Eindeutigkeit der Namen, verhindert das Vortäuschen von Namen (Spoofing) und stellt Aufrufern beim Auflösen eines Verweises eine eindeutige Identität bereit. Mit einem starken Namen ist jedoch keine Vertrauensebene verknüpft.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
> [!NOTE]
> All diese Funktionen sind ab .NET Framework 4 als veraltet markiert. Empfohlene Alternativen finden Sie in der [ICLRStrongName](../hosting/iclrstrongname-interface.md)-Schnittstelle.  
  
 [GetHashFromAssemblyFile-Funktion](gethashfromassemblyfile-function.md)  
 Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab. Ab .NET Framework 4 veraltet.  
  
 [GetHashFromAssemblyFileW-Funktion](gethashfromassemblyfilew-function.md)  
 Ruft einen Hash der als Unicode-Zeichenfolge angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab. Ab .NET Framework 4 veraltet.  
  
 [GetHashFromBlob-Funktion](gethashfromblob-function.md)  
 Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab. Ab .NET Framework 4 veraltet.  
  
 [GetHashFromFile-Funktion](gethashfromfile-function.md)  
 Generiert einen Hashwert für den Inhalt der angegebenen Datei.  Ab .NET Framework 4 veraltet.  
  
 [GetHashFromFileW-Funktion](gethashfromfilew-function.md)  
 Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei. Ab .NET Framework 4 veraltet.  
  
 [GetHashFromHandle-Funktion](gethashfromhandle-function.md)  
 Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.  Ab .NET Framework 4 veraltet.  
  
 [StrongNameCompareAssemblies-Funktion](strongnamecompareassemblies-function.md)  
 Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden. Ab .NET Framework 4 veraltet.  
  
 [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md)  
 Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.  
  
 [StrongNameFreeBuffer-Funktion](strongnamefreebuffer-function.md)  
 Gibt Speicher frei, der bei einem vorherigen Aufruf einer Funktion für starke Namen wie [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) oder [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) zugewiesen wurde.   Ab .NET Framework 4 veraltet.  
  
 [StrongNameGetBlob-Funktion](strongnamegetblob-function.md)  
 Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf. Ab .NET Framework 4 veraltet.  
  
 [StrongNameGetBlobFromImage-Funktion](strongnamegetblobfromimage-function.md)  
 Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab. Ab .NET Framework 4 veraltet.  
  
 [StrongNameGetPublicKey-Funktion](strongnamegetpublickey-function.md)  
 Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab. Ab .NET Framework 4 veraltet.  
  
 [StrongNameHashSize-Funktion](strongnamehashsize-function.md)  
 Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.  Ab .NET Framework 4 veraltet.  
  
 [StrongNameKeyDelete-Funktion](strongnamekeydelete-function.md)  
 Löscht den angegebenen Schlüsselcontainer. Ab .NET Framework 4 veraltet.  
  
 [StrongNameKeyGen-Funktion](strongnamekeygen-function.md)  
 Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.  Ab .NET Framework 4 veraltet.  
  
 [StrongNameKeyGenEx-Funktion](strongnamekeygenex-function.md)  
 Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung von starken Namen. Ab .NET Framework 4 veraltet.  
  
 [StrongNameKeyInstall-Funktion](strongnamekeyinstall-function.md)  
 Importiert ein öffentliches/privates Schlüsselpaar in einen Container.  Ab .NET Framework 4 veraltet.  
  
 [StrongNameSignatureGeneration-Funktion](strongnamesignaturegeneration-function.md)  
 Generiert eine Signatur mit starkem Namen für die angegebene Assembly.   Ab .NET Framework 4 veraltet.  
  
 [StrongNameSignatureGenerationEx-Funktion](strongnamesignaturegenerationex-function.md)  
 Generiert eine Signatur mit starkem Namen für die angegebene Assembly basierend auf den angegebenen Flags.    Ab .NET Framework 4 veraltet.  
  
 [StrongNameSignatureSize-Funktion](strongnamesignaturesize-function.md)  
 Gibt die Größe der Signatur mit starkem Namen zurück. Ab .NET Framework 4 veraltet.  
  
 [StrongNameSignatureVerification-Funktion](strongnamesignatureverification-function.md)  
 Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird. Ab .NET Framework 4 veraltet.  
  
 [StrongNameSignatureVerificationEx-Funktion](strongnamesignatureverificationex-function.md)  
 Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.  Ab .NET Framework 4 veraltet.  
  
 [StrongNameSignatureVerificationFromImage-Funktion](strongnamesignatureverificationfromimage-function.md)  
 Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist. Ab .NET Framework 4 veraltet.  
  
 [StrongNameTokenFromAssembly-Funktion](strongnametokenfromassembly-function.md)  
 Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.  Ab .NET Framework 4 veraltet.  
  
 [StrongNameTokenFromAssemblyEx-Funktion](strongnametokenfromassemblyex-function.md)  
 Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück. Ab .NET Framework 4 veraltet.  
  
 [StrongNameTokenFromPublicKey-Funktion](strongnametokenfrompublickey-function.md)  
 Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt. Ab .NET Framework 4 veraltet.  
  
 [PublicKeyBlob-Struktur](publickeyblob-structure.md)  
 Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im binären Format dar.  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
- [Referenz zur nicht verwalteten API](../index.md)
