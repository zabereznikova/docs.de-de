---
title: "Problemumgehung: PNG-Bilder in Symbolobjekten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Problemumgehung: PNG-Bilder in Symbolobjekten
Ab .NET Framework 4.6 konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>\-Methode Symbole mit PNG\-Bildern erfolgreich in <xref:System.Drawing.Bitmap>\-Objekte.  
  
 In Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>\-Methode eine <xref:System.ArgumentOutOfRangeException>\-Ausnahme aus, wenn das <xref:System.Drawing.Icon>\-Objekt PNG\-Bilder aufweist.  
  
## Auswirkungen  
 Diese Änderung betrifft Apps, die neu kompiliert werden, um sie auf .NET Framework 4.6 auszurichten, und die eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein <xref:System.Drawing.Icon>\-Objekt PNG\-Bilder aufweist. Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.  
  
### Problemumgehung  
 Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)\-Abschnitt Ihrer Datei „app.config“ hinzufügen:  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
  
```  
  
 Wenn die Datei „app.config“ bereits das `AppContextSwitchOverrides`\-Element enthält, muss der neue Wert wie folgt mit dem `value`\-Attribut zusammengeführt werden:  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
  
```  
  
## Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)