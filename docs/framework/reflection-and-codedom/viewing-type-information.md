---
title: "Anzeigen von Typinformationen | Microsoft Docs"
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
helpviewer_keywords: 
  - "Reflektion, Anzeigen von Typinformationen"
  - "Type-Objekt"
  - "Typen, Anzeigen von Typinformationen"
  - "Anzeigen von Typinformationen"
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Anzeigen von Typinformationen
Die <xref:System.Type?displayProperty=fullName>\-Klasse ist für die Reflektion von zentraler Bedeutung.   Auf Anforderung der Reflektion erstellt Common Language Runtime den **Type** für einen geladenen Typ.  Sie können die Methoden, Felder, Eigenschaften und geschachtelten Klassen dieses **Type**\-Objekts verwenden, um sämtliche Informationen über diesen Typ zu erhalten.  
  
 Mit <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> oder <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> können Sie **Type**\-Objekte nicht geladener Assemblys abrufen, indem Sie den Namen des gewünschten Typs bzw. der gewünschten Typen übergeben.  Mit <xref:System.Type.GetType%2A?displayProperty=fullName> können Sie **Type**\-Objekte einer bereits geladenen Assembly abrufen.  Mit <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName> und <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName> können Sie **Type**\-Modulobjekte abrufen.  
  
> [!NOTE]
>  Zusätzliche Informationen zum Überprüfen und Bearbeiten von generischen Typen und Methoden finden Sie unter [Reflektion und generische Typen](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) und [Gewusst wie: Untersuchen und Instanziieren von generischen Typen mit Reflektion](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 Das folgende Beispiel zeigt die Syntax, die erforderlich ist, um das <xref:System.Reflection.Assembly>\-Objekt und \-Modul für eine Assembly abzurufen.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 Im folgenden Beispiel werden die Namen von **Type**\-Objekten einer geladenen Assembly ausgegeben.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 Sobald Sie einen **Type** erhalten haben, gibt es viele Möglichkeiten, Informationen über die Member dieses Typs zu erhalten.  Um Informationen über alle Member eines Typs zu erhalten, können Sie z. B. die <xref:System.Type.GetMembers%2A?displayProperty=fullName>\-Methode aufrufen. Diese ruft wiederum ein Array von <xref:System.Reflection.MemberInfo>\-Objekten ab, die alle Member des aktuellen Typs beschreiben.  
  
 Sie können auch Methoden der **Type**\-Klasse verwenden, um Informationen über einen oder mehrere Konstruktoren, Methoden, Ereignisse, Felder oder Eigenschaften zu erhalten, die Sie mit Namen angeben.  <xref:System.Type.GetConstructor%2A?displayProperty=fullName> kapselt beispielsweise einen bestimmten Konstruktor der aktuellen Klasse.  
  
 Wenn Sie über einen **Type** verfügen, können Sie die <xref:System.Type.Module%2A?displayProperty=fullName>\-Eigenschaft verwenden, um ein Objekt abzurufen, das das Modul mit dem Typ kapselt.  Verwenden Sie die <xref:System.Reflection.Module.Assembly%2A?displayProperty=fullName>\-Eigenschaft zum Suchen eines Objekts, das die Assembly mit dem Modul kapselt.  Sie können die Assembly, die den Typ kapselt, mit der <xref:System.Type.Assembly%2A?displayProperty=fullName>\-Eigenschaft direkt abrufen.  
  
## System.Type und ConstructorInfo  
 Im folgenden Beispiel werden die Konstruktoren einer Klasse \(in diesem Fall der <xref:System.String>\-Klasse\) aufgelistet.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## MemberInfo, MethodInfo, FieldInfo und PropertyInfo  
 Informationen über die Methoden, Eigenschaften, Ereignisse und Felder eines Typs können Sie mit den Objekten <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> und <xref:System.Reflection.PropertyInfo> abrufen.  
  
 Im folgenden Beispiel wird **MemberInfo** verwendet, um die Anzahl der Member der **System.IO.File**\-Klasse aufzulisten. Die [System.Type.IsPublic](frlrfSystemTypeClassIsPublicTopic)\-Eigenschaft dient zum Bestimmen der Sichtbarkeit der Klasse.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 Im folgenden Beispiel wird der Typ eines angegebenen Members untersucht.  Für einen Member der **MemberInfo\-**Klasse wird Reflektion durchgeführt. Anschließend wird dessen Typ angezeigt.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 Im folgenden Beispiel werden die **\*Info**\-Klassen der Reflektion zusammen mit <xref:System.Reflection.BindingFlags> verwendet, um alle Member \(Konstruktoren, Felder, Eigenschaften, Ereignisse und Methoden\) der angegebenen Klasse aufzulisten. Die Member werden in statische und Instanzkategorien unterteilt.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## Siehe auch  
 <xref:System.Reflection.BindingFlags>   
 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.GetMembers%2A?displayProperty=fullName>   
 <xref:System.Type.GetFields%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Reflection.MemberInfo>   
 <xref:System.Reflection.ConstructorInfo>   
 <xref:System.Reflection.MethodInfo>   
 <xref:System.Reflection.FieldInfo>   
 <xref:System.Reflection.EventInfo>   
 <xref:System.Reflection.ParameterInfo>   
 [Reflektion und generische Typen](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)