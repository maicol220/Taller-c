import java.util.ArrayList;
import java.util.List;

public class Santuario {

    private List<Caballero> lista;

    public Santuario() {
        lista = new ArrayList<>();
        predefinir();
    }

    private void predefinir() {
        lista.add(new Caballero(1, "Seiya", "Bronce", "Pegaso", 7, "Proteger Atena", 3, 150000));
        lista.add(new Caballero(2, "Shiryu", "Bronce", "Dragón", 8, "Custodiar la cascada", 2, 120000));
        lista.add(new Caballero(3, "Aioria", "Oro", "Leo", 10, "Vigilar el templo", 5, 450000));
        lista.add(new Caballero(4, "Saga", "Oro", "Géminis", 10, "Equilibrar dimensiones", 5, 500000));
        lista.add(new Caballero(5, "Shun", "Bronce", "Andrómeda", 5, "Proteger Atena", 3, 150000));
    }

    public void agregar(Caballero c) {
        lista.add(c);
    }

    public boolean existeID(int id) {
        for (Caballero c : lista) {
            if (c.getId() == id) return true;
        }
        return false;
    }

    public Caballero buscarPorID(int id) {
        for (Caballero c : lista) {
            if (c.getId() == id) return c;
        }
        return null;
    }

    public void ordenarPorID() {
        Caballero aux;
        for (int i = 0; i < lista.size() - 1; i++) {
            for (int j = i + 1; j < lista.size(); j++) {
                if (lista.get(j).getId() < lista.get(i).getId()) {
                    aux = lista.get(i);
                    lista.set(i, lista.get(j));
                    lista.set(j, aux);
                }
            }
        }
    }

    public void ordenarPorNombre() {
        Caballero aux;
        for (int i = 0; i < lista.size() - 1; i++) {
            for (int j = i + 1; j < lista.size(); j++) {
                if (lista.get(j).getNombre().compareToIgnoreCase(lista.get(i).getNombre()) < 0) {
                    aux = lista.get(i);
                    lista.set(i, lista.get(j));
                    lista.set(j, aux);
                }
            }
        }
    }

    public void ordenarPorPoder() {
        Caballero aux;
        for (int i = 0; i < lista.size() - 1; i++) {
            for (int j = i + 1; j < lista.size(); j++) {
                if (lista.get(j).getNivelPoder() > lista.get(i).getNivelPoder()) {
                    aux = lista.get(i);
                    lista.set(i, lista.get(j));
                    lista.set(j, aux);
                }
            }
        }
    }

    public List<Caballero> getLista() {
        return lista;
    }
}

