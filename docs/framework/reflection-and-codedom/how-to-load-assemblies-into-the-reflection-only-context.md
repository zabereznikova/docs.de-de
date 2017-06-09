---
title: "Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Laden für Reflektion"
  - "Assemblys [.NET Framework], Reflektionsbezogener Ladekontext"
  - "Attribute [.NET Framework], Abrufen"
  - "Reflektion, Reflektionsbezogener Ladekontext"
  - "Reflektionsbezogener Ladekontext"
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext
Mit dem reflektionsbezogenen Ladekontext können Assemblys untersucht werden, die für andere Plattformen oder für andere Versionen von .NET Framework kompiliert wurden.  In diesen Kontext geladener Code kann nur untersucht, nicht jedoch ausgeführt werden.  Dies bedeutet, dass keine Objekte erstellt werden können, da die Konstruktoren nicht ausgeführt werden können.  Da der Code nicht ausgeführt werden kann, werden Abhängigkeiten nicht automatisch geladen.  Wenn Sie die Abhängigkeiten untersucht werden sollen, müssen Sie diese selbst laden.  
  
### So laden Sie eine Assembly in den reflektionsbezogenen Ladekontext  
  
1.  Laden Sie die Assembly mithilfe der <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29>\-Methodenüberladung, sofern der Anzeigename angegeben ist, oder mithilfe der <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>\-Methode, sofern der Pfad angegeben ist.  Wenn es sich bei der Assembly um ein binäres Bild handelt, verwenden Sie die [ReflectionOnlyLoad\(Byte\<xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>\-Methodenüberladung.  
  
    > [!NOTE]
    >  Sie können mit dem reflektionsbezogenen Kontext keine Version der mscorlib.dll aus einer anderen Version von .NET Framework als der Version im Ausführungskontext laden.  
  
2.  Wenn die Assembly über Abhängigkeiten verfügt, lädt die <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>\-Methode sie nicht.  Wenn Sie die Abhängigkeiten untersuchen müssen, müssen Sie diese selbst laden.  
  
3.  Mithilfe der <xref:System.Reflection.Assembly.ReflectionOnly%2A>\-Eigenschaft der Assembly können Sie ermitteln, ob eine Assembly in den reflektionsbezogenen Kontext geladen ist.  
  
4.  Wenn auf die Assembly oder die Typen in der Assembly Attribute angewendet wurden, untersuchen Sie diese Attribute mithilfe der <xref:System.Reflection.CustomAttributeData>\-Klasse, um zu gewährleisten, dass nicht versucht wird, Code im reflektionsbezogenen Kontext auszuführen.  Mit der entsprechenden Überladung der <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName>\-Methode rufen Sie die <xref:System.Reflection.CustomAttributeData>\-Objekte ab, die die Attribute darstellen, die auf eine Assembly, einen Member, ein Modul oder einen Parameter angewendet wurden.  
  
    > [!NOTE]
    >  Attribute, die auf die Assembly oder ihren Inhalt angewendet wurden, können in der Assembly oder in einer anderen Assembly definiert sein, die in den reflektionsbezogenen Kontext geladen ist.  Es kann nicht vorausgesagt werden, wo die Attribute definiert werden.  
  
## Beispiel  
 Im folgenden Beispielcode wird veranschaulicht, wie Sie die Attribute untersuchen, die auf eine in den reflektionsbezogenen Kontext geladene Assembly angewendet wurden.  
  
 Im Codebeispiel wird ein benutzerdefiniertes Attribut mit zwei Konstruktoren und einer Eigenschaft definiert.  Das Attribut wird auf die Assembly, einen in der Assembly deklarierten Typ, eine Methode des Typs und einen Parameter der Methode angewendet.  Bei der Ausführung lädt die Assembly sich selbst in den reflektionsbezogenen Kontext und zeigt Informationen über die benutzerdefinierten Attribute an, die auf sie und die enthaltenen Typen und Member angewendet wurden.  
  
> [!NOTE]
>  Um das Codebeispiel zu vereinfachen, lädt und untersucht sich die Assembly selbst.  Unter normalen Umständen würden Sie nicht erwarten, dass ein und dieselbe Assembly sowohl in den Ausführungskontext als auch in den reflektionsbezogenen Kontext geladen wird.  
  
 [!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
 [!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
 [!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]  
  
## Siehe auch  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 <xref:System.Reflection.Assembly.ReflectionOnly%2A>   
 <xref:System.Reflection.CustomAttributeData>