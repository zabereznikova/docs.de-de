---
title: ICeeGen-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: ae3c372951de00b097d0a8437039a3a85bf3aabf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426148"
---
# <a name="iceegen-interface"></a>ICeeGen-Schnittstelle
Stellt Methoden zur dynamischen Codekompilierung bereit.  
  
 Diese Schnittstelle ist veraltet und sollte nicht verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Veraltet. Fügt der Codebasis eine reloc-Anweisung hinzu.|  
|[AllocateMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Veraltet. Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode ab.|  
|[ComputePointer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Veraltet. Bestimmt den Puffer für den angegebenen Code Abschnitt.|  
|[EmitString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Veraltet. Gibt die angegebene Zeichenfolge in der Codebasis aus.|  
|[GenerateCeeFile-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Veraltet. Generiert eine Code Basisdatei, die die Codebasis enthält, die derzeit in diese `ICeeGen`geladen wird.|  
|[GenerateCeeMemoryImage-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Veraltet. Generiert ein Bild im Arbeitsspeicher für die Codebasis.|  
|[GetIlSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Veraltet. Ruft den Abschnitt der zwischen Sprachen-Codebasis ab, auf die vom angegebenen Handle verwiesen wird.|  
|[GetIMapTokenIface-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Veraltet. Ruft die Schnittstelle ab, auf die vom angegebenen Token verwiesen wird.|  
|[GetMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Veraltet. Ruft einen Puffer der entsprechenden Größe für die Methode an der angegebenen relativen virtuellen Adresse ab.|  
|[GetSectionBlock-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Veraltet. Ruft einen Abschnitts Block der Codebasis ab.|  
|[GetSectionCreate-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Veraltet. Generiert einen Code Abschnitt unter Verwendung des angegebenen Namens und der Flagwerte und ruft diesen ab.|  
|[GetSectionDataLen-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Veraltet. Ruft die Länge des angegebenen Abschnitts ab.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Veraltet. Ruft die Zeichenfolge ab, die bei der angegebenen relativen virtuellen Adresse gespeichert wird.|  
|[GetStringSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Veraltet. Ruft eine Zeichen folgen Darstellung des Code Abschnitts ab, auf den vom angegebenen Handle verwiesen wird.|  
|[TruncateSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Veraltet. Verkürzt den angegebenen Code Abschnitt um die angegebene Länge.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
