graph TD
    %% --- Subgrafos para cada Mundo ---
    subgraph Mundo 1
        W1_1("1-1") --> W1_2("1-2") --> W1_4("1-4 Castillo")
    end
    subgraph Mundo 2
        W2_1("2-1") --> W2_4("2-4 Castillo")
    end
    subgraph Mundo 3
        W3_1("3-1") --> W3_4("3-4 Castillo")
    end
    subgraph Mundo 4
        W4_1("4-1") --> W4_2("4-2") --> W4_4("4-4 Castillo")
    end
    subgraph Mundo 5
        W5_1("5-1") --> W5_4("5-4 Castillo")
    end
    subgraph Mundo 6
        W6_1("6-1") --> W6_4("6-4 Castillo")
    end
    subgraph Mundo 7
        W7_1("7-1") --> W7_4("7-4 Castillo")
    end
    subgraph Mundo 8
        W8_1("8-1") --> W8_2("8-2") --> W8_3("8-3") --> W8_4("8-4 Castillo Final")
    end

    FIN([VICTORIA])

    %% --- Conexiones de Caminos ---

    %% CAMINO COMPLETO (NORMAL)
    W1_4 --> W2_1
    W2_4 --> W3_1
    W3_4 --> W4_1
    W4_4 --> W5_1
    W5_4 --> W6_1
    W6_4 --> W7_1
    W7_4 --> W8_1
    W8_4 --> FIN

    %% ATAJOS Y CAMINO MÁS RÁPIDO
    % Warp Zone en 1-2
    W1_2 -- "Warp a Mundo 2" --> W2_1
    W1_2 -- "Warp a Mundo 3" --> W3_1
    W1_2 -- "Warp a Mundo 4" --> W4_1

    % Warp Zone en 4-2
    W4_2 -- "Warp a Mundo 5" --> W5_1
    W4_2 -- "Warp a Mundo 6" --> W6_1
    W4_2 -- "Warp a Mundo 7" --> W7_1
    W4_2 -- "Warp a Mundo 8" --> W8_1

    %% --- Estilos para Claridad ---
    % Estilo del camino más rápido (nodos verdes)
    style W1_1 fill:#9f9,stroke:#333,stroke-width:2px
    style W1_2 fill:#9f9,stroke:#333,stroke-width:2px
    style W4_1 fill:#9f9,stroke:#333,stroke-width:2px
    style W4_2 fill:#9f9,stroke:#333,stroke-width:2px
    style W8_1 fill:#9f9,stroke:#333,stroke-width:2px
    style W8_2 fill:#9f9,stroke:#333,stroke-width:2px
    style W8_3 fill:#9f9,stroke:#333,stroke-width:2px
    style W8_4 fill:#9f9,stroke:#333,stroke-width:2px
    style FIN fill:#9f9,stroke:#333,stroke-width:2px

    % Estilo de las conexiones (líneas)
    linkStyle default stroke:#ccc,stroke-width:1px,stroke-dasharray: 5 5
    % Conexiones del camino rápido (verde)
    linkStyle 0,11,2,21,5,6,7,14 stroke:green,stroke-width:3px
    % Conexiones de atajos alternativos (naranja)
    linkStyle 15,16,18,19,20 stroke:orange,stroke-width:2px
