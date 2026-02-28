# TUS-PR-CERES-FAVORITOS
Vota por tu procer favorito Venezolano

def votar_procer():
    # Diccionario con próceres y sus fechas
    proceres = {
        "Simón Bolívar": {"nacimiento": "1783", "muerte": "1830", "votos": 0},
        "Francisco de Miranda": {"nacimiento": "1750", "muerte": "1816", "votos": 0},
        "Antonio José de Sucre": {"nacimiento": "1795", "muerte": "1830", "votos": 0},
        "José Antonio Páez": {"nacimiento": "1790", "muerte": "1873", "votos": 0},
        "Rafael Urdaneta": {"nacimiento": "1788", "muerte": "1845", "votos": 0}
    }

    nombres = list(proceres.keys())

    while True:
        print("\n--- TU MEJOR PROCER VENEZOLANO ---")
        for i, nombre in enumerate(nombres, 1):
            info = proceres[nombre]
            print(f"{i}. {nombre} ({info['nacimiento']} - {info['muerte']}) | Votos: {info['votos']}")
        
        print(f"{len(nombres) + 1}. Salir y ver ganador")

        try:
            opcion = int(input("\nElige el número de tu prócer favorito: "))
            
            if 1 <= opcion <= len(nombres):
                seleccionado = nombres[opcion - 1]
                proceres[seleccionado]["votos"] += 1
                print(f"¡Voto registrado para {seleccionado}!")
            elif opcion == len(nombres) + 1:
                break
            else:
                print("Opción no válida.")
        except ValueError:
            print("Por favor, ingresa un número.")

    # Determinar ganador
    ganador = max(proceres, key=lambda x: proceres[x]["votos"])
    print(f"\n🏆 El prócer más votado fue: {ganador} con {proceres[ganador]['votos']} votos.")

if __name__ == "__main__":
    votar_procer()
