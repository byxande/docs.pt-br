---
title: "Como adicionar a funcionalidade de delimitação e bloqueio a uma coleção"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3258534cb0bf67b180080eca4f7cefc65c609fa4
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>Como adicionar a funcionalidade de delimitação e bloqueio a uma coleção
Este exemplo mostra como adicionar a funcionalidade de delimitação e de bloqueio a uma classe de coleção personalizada por meio da implementação da interface <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> na classe e do uso de uma instância da classe como o mecanismo de armazenamento interno para um <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>. Para obter mais informações sobre delimitação e bloqueio, veja [Visão geral de BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
## <a name="example"></a>Exemplo  
 A classe de coleção personalizada é uma fila de prioridade básica na qual os níveis de prioridade são representados como uma matriz de objetos <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>. Nenhuma solicitação adicional é executada dentro de cada fila.  
  
 No código do cliente, três tarefas são iniciadas. A primeira tarefa apenas monitora a digitação no teclado para permitir o cancelamento a qualquer momento durante a execução. A segunda tarefa é o thread produtor; ele adiciona novos itens na coleção de bloqueio e atribui uma prioridade com base em um valor aleatório a cada item. A terceira tarefa remove itens da coleção assim que eles ficarem disponíveis.  
  
 Você pode ajustar o comportamento do aplicativo fazendo com que um dos threads seja executado mais rapidamente do que o outro. Se o produtor for executado mais rapidamente, você observará que a funcionalidade delimitadora como a coleta de bloqueio impedirá que itens sejam adicionados se ela já contiver o número de itens especificado no construtor. Se o consumidor for executado mais rapidamente, você observará a funcionalidade de bloqueio enquanto o consumidor aguarda que um novo item seja adicionado.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 Por padrão, o armazenamento para um <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> é <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.  
  
## <a name="see-also"></a>Consulte também  
 [Coleções Thread-Safe](../../../../docs/standard/collections/thread-safe/index.md)

