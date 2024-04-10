def es_primo(numero):
    if numero <= 1:
        return False
    elif numero <= 3:
        return True
    elif numero % 2 == 0 or numero % 3 == 0:
        return False
    i = 5
    while i * i <= numero:
        if numero % i == 0 or numero % (i + 2) == 0:
            return False
        i += 6
    return True

# Pruebas
def test_es_primo():
    test_cases = [
        (2, True),
        (3, True),
        (5, True),
        (6, False)
    ]
    passed_tests = []
    failed_tests = []
    
    for num, expected_result in test_cases:
        try:
            assert es_primo(num) == expected_result
            passed_tests.append(num)
        except AssertionError:
            failed_tests.append(num)
    
    print("Pruebas exitosas:", passed_tests)
    print("Pruebas fallidas:", failed_tests)

test_es_primo()
