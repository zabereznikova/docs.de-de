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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fb081c48abf899b44da1c1351efa3f6036f1c8d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176123"
---
# <a name="iceegen-interface"></a>ICeeGen-Schnittstelle
Stellt Methoden zur dynamischen Codekompilierung bereit.  
  
 Diese Schnittstelle ist veraltet und sollte nicht verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Veraltet. Fügt eine .reloc-Anweisung in die Codebasis.|  
|[AllocateMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Veraltet. Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode.|  
|[ComputePointer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Veraltet. Bestimmt den Puffer für den angegebenen Codeabschnitt.|  
|[EmitString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Veraltet. Gibt die angegebene Zeichenfolge in die CodeBase.|  
|[GenerateCeeFile-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Veraltet. Generiert eine Codebasis-Datei, die derzeit geladene, in die Codebasis enthält `ICeeGen`.|  
|[GenerateCeeMemoryImage-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Veraltet. Generiert ein Image im Arbeitsspeicher für die Codebasis.|  
|[GetIlSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Veraltet. Ruft ab, der Teil der Zwischensprache Codebasis auf das angegebene Handle verweist.|  
|[GetIMapTokenIface-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Veraltet. Ruft die Schnittstelle, die durch das angegebene Token verwiesen wird.|  
|[GetMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Veraltet. Ruft einen Puffer von geeigneter Größe für die Methode an der angegebenen relativen virtuellen Adresse an.|  
|[GetSectionBlock-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Veraltet. Ruft einen Abschnittsblock im des Codes ab.|  
|[GetSectionCreate-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Veraltet. Wird generiert, und ruft einen Codeabschnitt, der mit dem angegebenen Namen und der Flagwerte.|  
|[GetSectionDataLen-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Veraltet. Ruft die Länge des angegebenen Abschnitts.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Veraltet. Ruft die Zeichenfolge, die an der angegebenen relativen virtuellen Adresse gespeichert.|  
|[GetStringSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Veraltet. Ruft eine Zeichenfolgendarstellung der Codeabschnitt, der auf die verwiesen wird durch das angegebene Handle ab.|  
|[TruncateSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Veraltet. Schneidet den angegebenen Codeabschnitt durch die angegebene Länge ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
