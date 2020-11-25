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
ms.openlocfilehash: 2c180a135608350b0feec3f419be98f4f428b186
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704512"
---
# <a name="iceegen-interface"></a>ICeeGen-Schnittstelle

Stellt Methoden zur dynamischen Codekompilierung bereit.  
  
 Diese Schnittstelle ist veraltet und sollte nicht verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[AddSectionReloc-Methode](iceegen-addsectionreloc-method.md)|Veraltet. Fügt der Codebasis eine reloc-Anweisung hinzu.|  
|[AllocateMethodBuffer-Methode](iceegen-allocatemethodbuffer-method.md)|Veraltet. Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode ab.|  
|[ComputePointer-Methode](iceegen-computepointer-method.md)|Veraltet. Bestimmt den Puffer für den angegebenen Code Abschnitt.|  
|[EmitString-Methode](iceegen-emitstring-method.md)|Veraltet. Gibt die angegebene Zeichenfolge in der Codebasis aus.|  
|[GenerateCeeFile-Methode](iceegen-generateceefile-method.md)|Veraltet. Generiert eine Code Basisdatei, die die Codebasis enthält, die derzeit in diese geladen wird `ICeeGen` .|  
|[GenerateCeeMemoryImage-Methode](iceegen-generateceememoryimage-method.md)|Veraltet. Generiert ein Bild im Arbeitsspeicher für die Codebasis.|  
|[GetIlSection-Methode](iceegen-getilsection-method.md)|Veraltet. Ruft den Abschnitt der zwischen Sprachen-Codebasis ab, auf die vom angegebenen Handle verwiesen wird.|  
|[GetIMapTokenIface-Methode](iceegen-getimaptokeniface-method.md)|Veraltet. Ruft die Schnittstelle ab, auf die vom angegebenen Token verwiesen wird.|  
|[GetMethodBuffer-Methode](iceegen-getmethodbuffer-method.md)|Veraltet. Ruft einen Puffer der entsprechenden Größe für die Methode an der angegebenen relativen virtuellen Adresse ab.|  
|[GetSectionBlock-Methode](iceegen-getsectionblock-method.md)|Veraltet. Ruft einen Abschnitts Block der Codebasis ab.|  
|[GetSectionCreate-Methode](iceegen-getsectioncreate-method.md)|Veraltet. Generiert einen Code Abschnitt unter Verwendung des angegebenen Namens und der Flagwerte und ruft diesen ab.|  
|[GetSectionDataLen-Methode](iceegen-getsectiondatalen-method.md)|Veraltet. Ruft die Länge des angegebenen Abschnitts ab.|  
|[GetString-Methode](iceegen-getstring-method.md)|Veraltet. Ruft die Zeichenfolge ab, die bei der angegebenen relativen virtuellen Adresse gespeichert wird.|  
|[GetStringSection-Methode](iceegen-getstringsection-method.md)|Veraltet. Ruft eine Zeichen folgen Darstellung des Code Abschnitts ab, auf den vom angegebenen Handle verwiesen wird.|  
|[TruncateSection-Methode](iceegen-truncatesection-method.md)|Veraltet. Verkürzt den angegebenen Code Abschnitt um die angegebene Länge.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenschnittstellen](metadata-interfaces.md)
