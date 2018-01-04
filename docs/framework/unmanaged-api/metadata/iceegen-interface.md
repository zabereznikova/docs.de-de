---
title: ICeeGen-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen
helpviewer_keywords: ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73af58ac55fd22e5b4f19f715cb0b1a137a640a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iceegen-interface"></a>ICeeGen-Schnittstelle
Stellt Methoden zur dynamischen Codekompilierung bereit.  
  
 Diese Schnittstelle ist veraltet und sollte nicht verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Veraltet. Die CodeBase hinzugefügt eine .reloc-Anweisung.|  
|[AllocateMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Veraltet. Erstellt einen Puffer der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode ab.|  
|[ComputePointer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Veraltet. Bestimmt den Puffer für den angegebenen Codeabschnitt.|  
|[EmitString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Veraltet. Gibt die angegebene Zeichenfolge in die CodeBase aus.|  
|[GenerateCeeFile-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Veraltet. Generiert eine Codebasis Datei, die gegenwärtig in diese geladenen Codebasis enthält `ICeeGen`.|  
|[GenerateCeeMemoryImage-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Veraltet. Generiert ein Image im Arbeitsspeicher für die CodeBase.|  
|[GetIlSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Veraltet. Ruft den Abschnitt der Codebasis intermediate Language auf dem angegebenen Handle verweist.|  
|[GetIMapTokenIface-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Veraltet. Ruft die Schnittstelle, die durch das angegebene Token verwiesen wird.|  
|[GetMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Veraltet. Ruft einen Puffer, der die geeignete Größe für die Methode an der angegebenen relativen virtuellen Adresse ab.|  
|[GetSectionBlock-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Veraltet. Ruft einen Abschnittsblock der CodeBase ab.|  
|[GetSectionCreate-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Veraltet. Wird generiert, und ruft einen Codeabschnitt, der mit dem angegebenen Namen und Flagwerte.|  
|[GetSectionDataLen-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Veraltet. Ruft die Länge des angegebenen Abschnitts ab.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Veraltet. Ruft die Zeichenfolge, die an der angegebenen relativen virtuellen Adresse gespeichert.|  
|[GetStringSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Veraltet. Ruft eine Zeichenfolgendarstellung der Codeabschnitt, der dem angegebenen Handle verweist.|  
|[TruncateSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Veraltet. Schneidet die im Abschnitt angegebenen Code anhand der angegebenen Länge ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
