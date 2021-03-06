---
title: "Introdução aos genéricos (Guia de Programação em C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d4fddd29135bfc15acedb8b89d577dc99a21e18a
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="introduction-to-generics-c-programming-guide"></a>Introdução aos genéricos (Guia de Programação em C#)
As classes e métodos genéricos combinam a capacidade de reutilização, a segurança de tipos e a eficiência de uma maneira que suas contrapartes não genéricas não conseguem. Os genéricos são usados com mais frequência com coleções e com os métodos que operam nelas. A versão 2.0 da biblioteca de classes do .NET Framework fornece um novo namespace, <xref:System.Collections.Generic>, que contém várias classes de coleção novas com base em genéricos. É recomendável que todos os aplicativos que se destinam ao [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 e posterior usem as novas classes de coleção genéricas em vez das contrapartes não genéricas mais antigas, como a <xref:System.Collections.ArrayList>. Para obter mais informações, consulte [Genéricos na biblioteca de Classes .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 É claro que você também pode criar tipos e métodos genéricos personalizados para fornecer suas próprias soluções e padrões de design generalizados que sejam fortemente tipados e eficientes. O exemplo de código a seguir mostra uma classe de lista vinculada genérica simples para fins de demonstração. (Na maioria dos casos, você deve usar a classe <xref:System.Collections.Generic.List%601>, fornecida pela biblioteca de classes .NET Framework, em vez de criar a sua própria classe). O parâmetro de tipo `T` é usado em vários locais em que um tipo concreto normalmente seria usado para indicar o tipo do item armazenado na lista. Ele é usado das seguintes maneiras:  
  
-   Como o tipo de um parâmetro de método no método `AddHead`.  
  
-   Como o tipo de retorno do método público `GetNext` e a propriedade `Data` na classe `Node` aninhada.  
  
-   Como o tipo de dados do membro particular na classe aninhada.  
  
 Observe que T está disponível para a classe `Node` aninhada. Quando `GenericList<T>` é instanciada com um tipo concreto, por exemplo como um `GenericList<int>`, cada ocorrência de `T` será substituída por `int`.  
  
 [!code-cs[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 O exemplo de código a seguir mostra como o código cliente usa a classe `GenericList<T>` genérica para criar uma lista de inteiros. Ao simplesmente alterar o argumento de tipo, o código a seguir poderia facilmente ser modificado para criar listas de cadeias de caracteres ou qualquer outro tipo personalizado:  
  
 [!code-cs[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Collections.Generic>   
 [Guia de Programação em C#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)

