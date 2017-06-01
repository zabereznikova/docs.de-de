---
title: "Link Demands | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], demands"
  - "demanded permissions"
  - "permissions [.NET Framework], demands"
  - "granting permissions, demands"
  - "code access security, demands"
  - "user demands for permission"
  - "caller security checks"
  - "link demands"
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Link Demands
Ein Linkaufruf \(Verknüpfungsaufruf\) bewirkt eine Sicherheitsüberprüfung während der Just\-In\-Time\-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird.  Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird.  Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst.   Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.  
  
 Beachten Sie, dass bei diesem Typ von Forderung kein vollständiger Stackwalk durchgeführt wird und der Code weiterhin anfällig für Täuschungsmanöver ist.  Wenn beispielsweise eine Methode in Assembly A durch einen Linkaufruf geschützt ist, wird ein direkter Aufrufer in Assembly B ausgehend von den Berechtigungen der Assembly B ausgewertet.  Der Linkaufruf wertet jedoch keine Methode in Assembly C aus, wenn er über die Methode in Assembly B indirekt die Methode in Assembly A aufruft.  Der Linkaufruf gibt nur die Berechtigungen an, die direkte Aufrufer in der unmittelbar aufrufenden Assembly haben müssen, um zu Ihrem Code zu verlinken.  Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.  
  
 Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.  Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.  
  
 Wenn auf eine durch einen Linkaufruf geschützte Methode über [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md) in .NET Framework zugegriffen wird, überprüft ein Linkaufruf den direkten Aufrufer des Codes, auf den über Reflektion zugegriffen wird.  Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden.  Angenommen, Code verwendet Reflektion dazu, ein <xref:System.Reflection.MethodInfo>\-Objekt zurückzugeben, das eine durch einen Linkaufruf geschützte Methode darstellt, und übergibt dieses **MethodInfo**\-Objekt anschließend an anderen Code, der das Objekt dazu verwendet, die ursprüngliche Methode aufzurufen.  In diesem Fall wird die Linkaufrufüberprüfung zweimal durchgeführt: einmal für den Code, der das **MethodInfo\-Objekt** zurückgibt, und einmal für den Code, der dieses Objekt aufruft.  
  
> [!NOTE]
>  Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden.  Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.  
  
 Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`\-Methode die `CustomPermission`\-Berechtigung haben muss.  Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden.  Die Forderung wird vorgenommen, indem ein **SecurityAction.LinkDemand**\-Flag an das `CustomPermissionAttribute` übergeben wird.  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## Siehe auch  
 [Attribute](../../../docs/standard/attributes/index.md)   
 [Code Access Security](../../../docs/framework/misc/code-access-security.md)