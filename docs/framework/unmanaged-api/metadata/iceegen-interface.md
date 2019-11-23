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
  
 This interface is obsolete and should not be used.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Veraltet. Adds a .reloc instruction to the code base.|  
|[AllocateMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Veraltet. Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.|  
|[ComputePointer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Veraltet. Determines the buffer for the specified code section.|  
|[EmitString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Veraltet. Emits the specified string into the code base.|  
|[GenerateCeeFile-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Veraltet. Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.|  
|[GenerateCeeMemoryImage-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Veraltet. Generates an image in memory for the code base.|  
|[GetIlSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Veraltet. Gets the section of the intermediate language code base referenced by the specified handle.|  
|[GetIMapTokenIface-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Veraltet. Gets the interface referenced by the specified token.|  
|[GetMethodBuffer-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Veraltet. Gets a buffer of the appropriate size for the method at the specified relative virtual address.|  
|[GetSectionBlock-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Veraltet. Gets a section block of the code base.|  
|[GetSectionCreate-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Veraltet. Generates and gets a code section using the specified name and flag values.|  
|[GetSectionDataLen-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Veraltet. Gets the length of the specified section.|  
|[GetString-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Veraltet. Gets the string stored at the specified relative virtual address.|  
|[GetStringSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Veraltet. Gets a string representation of the code section referenced by the specified handle.|  
|[TruncateSection-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Veraltet. Truncates the specified code section by the specified length.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
