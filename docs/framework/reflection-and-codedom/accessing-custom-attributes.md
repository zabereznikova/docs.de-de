---
title: "Zugreifen auf benutzerdefinierte Attribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Attribute [.NET Framework], Aufrufen"
  - "Benutzerdefinierte Attribute, Barrierefreiheit"
  - "Reflektion, Benutzerdefinierte Attribute"
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Zugreifen auf benutzerdefinierte Attribute
Nach der Verknüpfung von Attributen mit Programmelementen ist es möglich, ihr Vorhandensein sowie ihre Werte unter Verwendung von Reflektion abzufragen.  In den .NET Framework\-Versionen 1.0 und 1.1 werden benutzerdefinierte Attribute im Ausführungskontext untersucht.  In .NET Framework, Version 2.0 steht ein neuer Load\-Kontext, der reflektionsbezogene Kontext zur Verfügung, um Code zu untersuchen, der nicht für die Ausführung geladen werden kann.  
  
## Reflektionsbezogener Kontext  
 Code, der in den reflektionsbezogenen Kontext geladen wird, kann nicht ausgeführt werden.  Daher können keine Instanzen benutzerdefinierter Attribute erstellt werden, da hierfür die zugehörigen Konstruktoren ausgeführt werden müssten.  Benutzerdefinierte Attribute können im reflektionsbezogenen Kontext mithilfe der <xref:System.Reflection.CustomAttributeData>\-Klasse geladen und untersucht werden.  Sie können Instanzen dieser Klasse durch die entsprechende Überladung der statischen <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName>\-Methode erhalten.  Siehe [Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
## Ausführungskontext  
 Die Hauptreflektionsmethoden zum Abfragen von Attributen im Ausführungskontext sind <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName> und <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>.  
  
 Die Zugriffsmöglichkeit auf ein benutzerdefiniertes Attribut wird unter Berücksichtigung der Assembly geprüft, mit der es verknüpft ist.  Äquivalent dazu ist die Überprüfung, ob eine Methode für einen Typ in der Assembly, mit der das benutzerdefinierte Attribut verknüpft ist, den Konstruktor des benutzerdefinierten Attributs aufrufen kann.  
  
 Methoden wie <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=fullName> überprüfen die Sichtbarkeit und den Zugriff des Typarguments.  Nur Code in der Assembly, die den benutzerdefinierten Typ enthält, kann mithilfe von **GetCustomAttributes** ein benutzerdefiniertes Attribut dieses Typs abrufen.  
  
 Das folgende C\#\-Beispiel ist ein typisches Entwurfsmuster für ein benutzerdefiniertes Attribut.  Das Beispiel verdeutlicht das Reflektionsmodell der Common Language Runtime mit benutzerdefinierten Attributen.  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 Wenn die Laufzeit versucht, die benutzerdefinierten Attribute für den öffentlichen benutzerdefinierten Attributtyp <xref:System.ComponentModel.DescriptionAttribute> abzurufen, der mit der **GetLanguage**\-Methode verknüpft ist, werden folgende Aktionen durchgeführt:  
  
1.  Common Language Runtime überprüft, ob das Typargument **DescriptionAttribute** für **Type.GetCustomAttributes** \(Type *Typ*\) öffentlich ist, d. h. sichtbar und erreichbar.  
  
2.  Common Language Runtime überprüft, ob der von der **DescriptionAttribute** abgeleitete benutzerdefinierte **MyDescriptionAttribute**\-Typ innerhalb der **System.Web.DLL**\-Assembly sichtbar und erreichbar ist. Darin ist der **MyDescriptionAttribute**\-Typ mit der GetLanguage\(\)\-Methode verknüpft.  
  
3.  Common Language Runtime überprüft, ob der Konstruktor von **MyDescriptionAttribute** innerhalb der **System.Web.DLL\-**Assembly sichtbar und erreichbar ist.  
  
4.  Common Language Runtime ruft den Konstruktor von **MyDescriptionAttribute** mit den benutzerdefinierten Attributparametern auf und gibt das neue Objekt an den Anrufer zurück.  
  
 Durch das Reflektionsmodell mit benutzerdefinierten Attributen können Instanzen benutzerdefinierter Typen aus der Assembly verloren gehen, in der der Typ definiert ist.  Dies gilt auch für Member der Laufzeitsystembibliothek, die Instanzen benutzerdefinierter Typen zurückgeben, z. B. [Type.GetMethods\(\)](frlrfSystemTypeClassGetMethodsTopic), wodurch die Rückgabe eines Arrays von **RuntimeMethodInfo**\-Objekten erfolgt.  Um zu verhindern, dass ein Client Informationen über einen benutzerdefinierten Attributtyp ermitteln kann, müssen Sie die Member dieses Typs als nicht öffentlich definieren.  
  
 Folgendes Beispiel zeigt, wie Reflektion im Prinzip verwendet werden kann, um Zugriff auf benutzerdefinierte Attribute zu erhalten.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## Siehe auch  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Anzeigen von Typinformationen](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Sicherheitsüberlegungen für die Reflektion](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)