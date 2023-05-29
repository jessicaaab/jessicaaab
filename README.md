import networkx as nx
import matplotlib.pyplot as plt

# Crear el grafo
G = nx.Graph()

# Agregar nodos
G.add_nodes_from(["Psicopedagogía", "Interdisciplinariedad", "Vulnerabilidad social",
                  "Psicopedagogía sociocomunitaria", "Enfoque potencializador y autonomizante",
                  "Organismos públicos", "Trabajo colaborativo", "Empoderamiento",
                  "Resiliencia sociocomunitaria"])

# Agregar aristas
G.add_edges_from([("Psicopedagogía", "Interdisciplinariedad"),
                  ("Psicopedagogía", "Vulnerabilidad social"),
                  ("Psicopedagogía sociocomunitaria", "Enfoque potencializador y autonomizante"),
                  ("Psicopedagogía sociocomunitaria", "Trabajo colaborativo"),
                  ("Psicopedagogía sociocomunitaria", "Empoderamiento"),
                  ("Vulnerabilidad social", "Organismos públicos"),
                  ("Resiliencia sociocomunitaria", "Empoderamiento")])

# Establecer posiciones de los nodos
pos = nx.spring_layout(G)

# Definir colores y tamaños de los nodos
node_colors = ["lightblue"] * 3 + ["lightgreen"] * 6
node_sizes = [800] * 3 + [600] * 6

# Dibujar el grafo
nx.draw_networkx(G, pos, node_color=node_colors, node_size=node_sizes,
                 with_labels=True, font_size=10, font_weight="bold")

# Guardar la imagen en formato PNG
plt.savefig("red_conceptual.png", dpi=300)
