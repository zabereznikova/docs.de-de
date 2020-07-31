---
title: Zugreifen auf benutzerdefinierte Attribute
description: Hier erfahren Sie, wie Sie in .NET auf benutzerdefinierte Attribute zugreifen. Nachdem Attribute Programmierelementen zugeordnet worden sind, können Sie die Reflexion verwenden, um deren Existenz und Werte abzufragen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
ms.openlocfilehash: 1197fc5149e144d293deda1173e82ca2dadeda7d
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475137"
---
# <a name="accessing-custom-attributes"></a>Zugreifen auf benutzerdefinierte Attribute
Nachdem Attribute Programmierelementen zugeordnet worden sind, kann Reflektion benutzt werden, um deren Existenz und Werte abzufragen. In der .NET Framework Version 1.0 und 1.1 werden benutzerdefinierte Attribute im Ausführungskontext untersucht. Die .NET Framework Version 2.0 stellt einen neuen Ladekontext bereit, den reflektionsbezogener Ladekontext, der zum Untersuchen von Code benutzt werden kann, der nicht für die Ausführung geladen werden kann.  
  
## <a name="the-reflection-only-context"></a>Der reflektionsbezogene Ladekontext  
 Code, der in den reflektionsbezogenen Ladekontext geladen wird, kann nicht ausgeführt werden. Das bedeutet, dass Instanzen von benutzerdefinierten Attributen nicht erstellt werden können, da dies die Ausführung deren Konstruktoren erfordern würde. Um benutzerdefinierte Attribute im reflektionsbezogenen Kontext zu laden, verwenden Sie die <xref:System.Reflection.CustomAttributeData>-Klasse. Sie können Instanzen dieser Klasse abrufen, indem Sie die geeignete Überladung der statistischen <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType>-Methode verwenden. Weitere Informationen finden Sie unter [How to: Laden von Assemblys in den reflexionsbezogenen Kontext](how-to-load-assemblies-into-the-reflection-only-context.md).  
  
## <a name="the-execution-context"></a>Der Ausführungskontext  
 Die wichtigsten Reflektionsmethoden zum Abfragen von Attributen im Ausführungskontext sind <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> und <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.  
  
 Die Überprüfung der Erreichbarkeit eines benutzerdefinierten Attributs erfolgt unter Berücksichtigung der Assembly, in der es angefügt ist. Dies entspricht der Überprüfung, ob eine Methode auf einem Typ in der Assembly, in der das benutzerdefinierte Attribut angefügt ist, den Konstruktor des benutzerdefinierten Attributs aufrufen kann.  
  
 Methoden wie <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> überprüfen die Sichtbarkeit und die Erreichbarkeit des Typarguments. Nur Code in der Assembly, der den benutzerdefinierten Typ enthält, kann ein benutzerdefiniertes Attribut dieses Typs mithilfe von **GetCustomAttributes** abrufen.  
  
 Das folgende C#-Beispiel ist ein typisches Entwurfsmuster eines benutzerdefinierten Attributs. Es stellt das Runtimemodell der Reflektion des benutzerdefinierten Attributs dar.  
  
```csharp
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
  
 Wenn die Runtime versucht, die benutzerdefinierten Attribute für den öffentlichen benutzerdefinierten Attributtyp <xref:System.ComponentModel.DescriptionAttribute> abzurufen, der an die **GetLanguage**-Methode angefügt ist, werden folgende Aktionen ausgeführt:  
  
1. Die Runtime überprüft, dass das Typargument **DescriptionAttribute** für **Type.GetCustomAttributes** (Typ *type*) öffentlich und somit sichtbar und erreichbar ist.  
  
2. Die Runtime überprüft, dass der benutzerdefinierte Typ **MyDescriptionAttribute**, der von **DescriptionAttribute** abgeleitet wurde, in der Assembly **System.Web.DLL** sichtbar und erreichbar ist, wo er an die Methode **GetLanguage**() angefügt ist.  
  
3. Die Runtime überprüft, dass der Konstruktor von **MyDescriptionAttribute** innerhalb der **System.Web.DLL**-Assembly sichtbar und erreichbar ist.  
  
4. Die Runtime ruft den Konstruktor von **MyDescriptionAttribute** mit den benutzerdefinierten Attributparametern auf und gibt dem Aufrufer das neue Objekt zurück.  
  
 Dem Reflektionsmodell des benutzerdefinierten Attributs könnten Instanzen von benutzerdefinierten Typen außerhalb der Assembly fehlen, in der der Typ definiert ist. Hier besteht kein Unterschied zu den Membern in der Runtimesystembibliothek, die Instanzen benutzerdefinierter Typen zurückgeben, z.B. <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>, die ein Array von **RuntimeMethodInfo**-Objekten zurückgibt. Um zu verhindern, dass ein Client Informationen über einen benutzerdefinierten Typ eines benutzerdefinierten Attributs ermittelt, definieren Sie, dass die Member des Typen nicht öffentlich sein sollen.  
  
 Das folgende Beispiel zeigt die einfachste Möglichkeit, Reflektion zu verwenden, um Zugriff auf benutzerdefinierte Attribute zu erhalten.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [Anzeigen von Typinformationen](viewing-type-information.md)
- [Security Considerations for Reflection (Sicherheitsüberlegungen für die Reflektion)](security-considerations-for-reflection.md)
