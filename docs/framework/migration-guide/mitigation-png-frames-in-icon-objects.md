---
title: 'Entschärfung: PNG-Bilder in Symbolobjekten'
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
ms.openlocfilehash: 1a4ae0c069a4cd6d53bce77e64822ebf3fbb5361
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457870"
---
# <a name="mitigation-png-frames-in-icon-objects"></a>Entschärfung: PNG-Bilder in Symbolobjekten
Ab .NET Framework 4.6 konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> -Methode Symbole mit PNG-Bildern erfolgreich in <xref:System.Drawing.Bitmap> -Objekte.  
  
 In Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> -Methode eine <xref:System.ArgumentOutOfRangeException> -Ausnahme aus, wenn das <xref:System.Drawing.Icon> -Objekt PNG-Bilder aufweist.  
  
## <a name="impact"></a>Auswirkungen  
 Diese Änderung betrifft Apps, die neu kompiliert werden, um sie auf .NET Framework 4.6 auszurichten, und die eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein <xref:System.Drawing.Icon> -Objekt PNG-Bilder aufweist. Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.  
  
### <a name="mitigation"></a>Minderung  
 Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt Ihrer app.config-Datei hinzufügen:  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 Wenn die Datei „app.config“ bereits das `AppContextSwitchOverrides`-Element enthält, muss der neue Wert wie folgt mit dem `value`-Attribut zusammengeführt werden:  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
