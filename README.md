# project
package com.java.shop;

import java.util.Map;

public class User {

	private String username;
	private String password;
	public String[][] accounts = { { "shopowner", "shopper" } };

	public User(String user, String pass) {
		username = user;
		password = pass;
	}

	/**
	 * Method to authenticate the user..
	 * 
	 * @param users
	 * @return
	 */
	public boolean authenticate(Map users) {
		if (users.keySet().size() > 0) {
			if (users.keySet().contains(username)) {
				if ((password.equals(users.get(username)))) {
					return true;
				}
			}
		}
		return false;
	}

	/**
	 * Method to check if store ids exist for the current shop owner or not
	 * 
	 * @param stores
	 * @param storeid
	 * @return
	 */
	public boolean checkStores(Map stores, String storeid) {
		if (stores.keySet().size() > 0) {
			if (stores.keySet().contains(storeid)) {
				if (("true".equals(stores.get(storeid)))) {
					return true;
				}
			}
		}
		return false;
	}

}
